# CONEXÃO COM O BANCO DE DADOS E CRIAÇÃO DA CLASSE ALUNO
Conectar-se a um banco de dados e criar uma classe de entidade, como a classe "Aluno", é uma parte fundamental no desenvolvimento de aplicativos Spring Boot que envolvem armazenamento de dados. Vou guiá-lo pelos passos necessários para realizar essas tarefas:

**Passo 1: Configurar o Banco de Dados**

1. Abra o arquivo `application.properties` ou `application.yml` em seu projeto Spring Boot. Este arquivo contém as configurações do aplicativo, incluindo as configurações do banco de dados.

2. Configure as propriedades do banco de dados, como o URL, nome de usuário e senha. Por exemplo, se você estiver usando um banco de dados H2 embutido, suas configurações podem ser semelhantes a estas:

Para `application.properties`:

```properties
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
```

Para `application.yml`:

```yaml
spring:
  datasource:
    url: jdbc:h2:mem:testdb
    driverClassName: org.h2.Driver
    username: sa
    password: password
```

Lembre-se de que você deve substituir essas configurações pelo URL, nome de usuário e senha do seu banco de dados específico, se estiver usando um banco de dados diferente.

**Passo 2: Criar a Classe Aluno como uma Entidade**

1. Crie uma classe Java para representar a entidade "Aluno". Essa classe deve ser anotada com `@Entity` para indicar que é uma entidade JPA (Java Persistence API).

```java
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;

@Entity
public class Aluno {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String nome;
    private int idade;

    // Construtores, getters e setters
}
```

Neste exemplo, a classe "Aluno" possui três campos: `id`, `nome` e `idade`. O campo `id` é anotado com `@Id` para indicar que é a chave primária da entidade, e `@GeneratedValue` é usado para gerar automaticamente o valor da chave primária.

**Passo 3: Criar um Repositório para Aluno**

1. Crie uma interface de repositório para a entidade "Aluno". O Spring Data JPA facilita a criação de repositórios para acessar os dados do banco de dados. Por exemplo:

```java
import org.springframework.data.jpa.repository.JpaRepository;

public interface AlunoRepository extends JpaRepository<Aluno, Long> {
}
```

A interface `AlunoRepository` estende `JpaRepository` e usa a classe "Aluno" e o tipo de dado da chave primária (`Long`) como argumentos de tipo.

**Passo 4: Usar o Repositório em um Controlador**

1. Crie um controlador Spring Boot que use o repositório "Aluno" para realizar operações de leitura e gravação no banco de dados. Por exemplo:

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class AlunoController {

    @Autowired
    private AlunoRepository alunoRepository;

    @GetMapping("/alunos")
    public String listarAlunos(Model model) {
        Iterable<Aluno> alunos = alunoRepository.findAll();
        model.addAttribute("alunos", alunos);
        return "lista_alunos";
    }
}
```

Neste exemplo, o controlador mapeia a URL `/alunos` para listar todos os alunos no banco de dados e passa os alunos para um modelo para renderização em uma página HTML.

**Passo 5: Criar a Página HTML**

1. Crie uma página HTML (por exemplo, `lista_alunos.html`) na pasta `src/main/resources/templates` do seu projeto para exibir a lista de alunos. Você pode usar Thymeleaf para exibir os dados na página.

```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Lista de Alunos</title>
</head>
<body>
    <h1>Lista de Alunos</h1>
    <ul>
        <li th:each="aluno : ${alunos}">
            <span th:text="${aluno.nome}"></span> - <span th:text="${aluno.idade}"></span> anos
        </li>
    </ul>
</body>
</html>
```

**Passo 6: Testar e Acessar a Página**

1. Inicie ou reinicie seu aplicativo Spring Boot.

2. Acesse a URL correspondente à página de lista de alunos (por exemplo, `http://localhost:8080/alunos`) em um navegador da web.

Você verá a lista de alunos sendo exibida na página HTML. Agora, você tem uma conexão com o banco de dados configurada e uma entidade "Aluno" criada para realizar operações de leitura no banco de dados. Você pode expandir isso para incluir operações de gravação, atualização e exclusão, conforme necessário.