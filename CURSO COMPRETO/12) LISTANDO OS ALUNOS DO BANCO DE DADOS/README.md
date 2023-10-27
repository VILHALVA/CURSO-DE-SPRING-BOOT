# LISTANDO OS ALUNOS DO BANCO DE DADOS
Listar os alunos do banco de dados em um aplicativo Spring Boot é uma operação comum e importante para exibir informações ao usuário. Vou mostrar como listar os alunos do banco de dados usando o Spring Boot e o Spring Data JPA.

**Passo 1: Configurar um Controlador**

Você pode criar um controlador Spring Boot para lidar com a listagem dos alunos. Neste exemplo, vamos criar um controlador que mapeia a URL `/alunos` para listar todos os alunos.

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

Neste exemplo, o controlador utiliza o repositório `AlunoRepository` para buscar todos os alunos no banco de dados e, em seguida, os adiciona ao modelo para renderização na página.

**Passo 2: Criar uma Página HTML para Exibir a Lista**

Agora, você precisa criar uma página HTML para exibir a lista de alunos. Esta página pode ser criada na pasta `src/main/resources/templates`. Vamos chamá-la de `lista_alunos.html`. Use Thymeleaf para iterar sobre a lista de alunos e exibi-los na página.

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

Neste exemplo, usamos `th:each` para iterar sobre a lista de alunos e exibir seus nomes e idades na página.

**Passo 3: Testar a Listagem de Alunos**

Inicie ou reinicie seu aplicativo Spring Boot e acesse a URL `/alunos` em um navegador da web. Você verá a lista de alunos do banco de dados sendo exibida na página.

Este é um exemplo simples de como listar alunos do banco de dados em um aplicativo Spring Boot. Você pode aprimorar isso com filtros, ordenação e paginação, dependendo dos requisitos do seu projeto.