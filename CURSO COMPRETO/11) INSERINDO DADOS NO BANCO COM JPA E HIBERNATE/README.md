# INSERINDO DADOS NO BANCO COM JPA E HIBERNATE
Inserir dados no banco de dados com o Spring Boot, JPA (Java Persistence API) e Hibernate é uma tarefa fundamental ao desenvolver aplicativos que envolvem persistência de dados. Vou guiá-lo pelos passos para inserir dados no banco usando essas tecnologias:

**Passo 1: Configurar a Entidade**

Antes de inserir dados no banco, é importante configurar a entidade que representa os dados que você deseja persistir. Vamos continuar usando o exemplo da classe "Aluno".

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

Certifique-se de que a classe `Aluno` esteja devidamente anotada com `@Entity`, com uma chave primária anotada com `@Id`.

**Passo 2: Criar um Repositório**

A próxima etapa é criar um repositório que estende a interface `JpaRepository` para a entidade `Aluno`. O repositório fornecerá métodos para realizar operações de inserção no banco de dados.

```java
import org.springframework.data.jpa.repository.JpaRepository;

public interface AlunoRepository extends JpaRepository<Aluno, Long> {
}
```

**Passo 3: Inserir Dados no Banco**

Você pode inserir dados no banco de dados usando o repositório. Isso pode ser feito em um controlador, serviço ou em qualquer parte do código onde seja necessário adicionar um novo aluno. Aqui está um exemplo de como inserir um novo aluno:

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class AlunoController {

    @Autowired
    private AlunoRepository alunoRepository;

    @PostMapping("/alunos")
    public Aluno adicionarAluno(@RequestBody Aluno aluno) {
        return alunoRepository.save(aluno);
    }
}
```

Neste exemplo, um novo aluno é inserido no banco de dados quando uma solicitação POST é feita para a URL `/alunos`. O método `save` do repositório é usado para inserir o aluno no banco.

**Passo 4: Enviar uma Solicitação POST**

Para inserir um novo aluno, você pode usar um cliente HTTP, como o Postman, ou até mesmo um formulário HTML em sua aplicação web para enviar uma solicitação POST para a URL `/alunos`. Certifique-se de que os dados do aluno sejam enviados no corpo da solicitação em formato JSON.

**Passo 5: Testar a Inserção de Dados**

Inicie ou reinicie seu aplicativo Spring Boot e, em seguida, envie uma solicitação POST para a URL `/alunos` com os dados do aluno. Por exemplo:

```json
{
    "nome": "João",
    "idade": 25
}
```

Você deve receber uma resposta com os detalhes do aluno recém-inserido, incluindo o ID gerado pelo banco de dados.

Isso completa o processo de inserção de dados no banco de dados usando o Spring Boot, JPA e Hibernate. Você pode continuar aprimorando seu aplicativo para realizar operações de leitura, atualização e exclusão, conforme necessário, além de implementar validações e tratamento de erros.