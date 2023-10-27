# MÉTODO EDITAR E EXCLUIR ALUNO
Criar métodos para editar e excluir alunos em um aplicativo Spring Boot é uma parte importante de qualquer sistema de gerenciamento de dados. Vou explicar como implementar essas funcionalidades no seu aplicativo.

**Método Editar Aluno**

Para editar um aluno, você precisará criar um formulário de edição e um controlador que aceite os dados do formulário e atualize as informações do aluno no banco de dados. Vamos passo a passo:

**Passo 1: Criar um Formulário de Edição**

Crie um formulário HTML que permita a edição dos dados do aluno. Você pode criar uma página HTML que exiba os detalhes do aluno e incluir um botão "Editar" que, ao ser clicado, levará o usuário a um formulário de edição.

Por exemplo, você pode criar uma página chamada `editar_aluno.html` que inclui um formulário para editar o nome e a idade do aluno.

```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Editar Aluno</title>
</head>
<body>
    <h1>Editar Aluno</h1>
    <form th:action="@{/alunos/editar}" method="post">
        <input type="hidden" th:field="*{id}" />
        Nome: <input type="text" th:field="*{nome}" /><br>
        Idade: <input type="number" th:field="*{idade}" /><br>
        <input type="submit" value="Salvar" />
    </form>
</body>
</html>
```

**Passo 2: Criar um Controlador para Edição**

Crie um controlador que mapeie a URL `/alunos/editar` para a página de edição e aceite os dados do formulário. O controlador deve atualizar as informações do aluno no banco de dados.

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.ModelAttribute;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.ui.Model;

@Controller
public class AlunoController {

    @Autowired
    private AlunoRepository alunoRepository;

    @GetMapping("/alunos/editar/{id}")
    public String editarAluno(@PathVariable Long id, Model model) {
        Aluno aluno = alunoRepository.findById(id).orElse(null);
        if (aluno == null) {
            // Tratar o caso em que o aluno não é encontrado
        } else {
            model.addAttribute("aluno", aluno);
            return "editar_aluno";
        }
    }

    @PostMapping("/alunos/editar")
    public String salvarEdicaoAluno(@ModelAttribute Aluno aluno) {
        alunoRepository.save(aluno);
        return "redirect:/alunos";
    }
}
```

**Método Excluir Aluno**

Para excluir um aluno, você precisará criar uma página de confirmação de exclusão e um controlador que aceite a solicitação de exclusão e remova o aluno do banco de dados. Vamos passo a passo:

**Passo 1: Criar uma Página de Confirmação de Exclusão**

Crie uma página HTML que exiba uma mensagem de confirmação de exclusão e inclua um botão "Confirmar Exclusão" e outro "Cancelar" para que o usuário confirme a ação.

Por exemplo, você pode criar uma página chamada `confirmar_exclusao.html` com o seguinte conteúdo:

```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Confirmar Exclusão</title>
</head>
<body>
    <h1>Confirmar Exclusão</h1>
    <p>Tem certeza de que deseja excluir este aluno?</p>
    <form th:action="@{/alunos/excluir}" method="post">
        <input type="hidden" th:field="*{id}" />
        <input type="submit" value="Confirmar Exclusão" />
    </form>
    <a th:href="@{/alunos}">Cancelar</a>
</body>
</html>
```

**Passo 2: Criar um Controlador para Exclusão**

Crie um controlador que mapeie a URL `/alunos/excluir/{id}` para a página de confirmação de exclusão e mapeie a URL `/alunos/excluir` para a exclusão do aluno no banco de dados.

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.ui.Model;

@Controller
public class AlunoController {

    @Autowired
    private AlunoRepository alunoRepository;

    @GetMapping("/alunos/excluir/{id}")
    public String confirmarExclusao(@PathVariable Long id, Model model)

 {
        Aluno aluno = alunoRepository.findById(id).orElse(null);
        if (aluno == null) {
            // Tratar o caso em que o aluno não é encontrado
        } else {
            model.addAttribute("aluno", aluno);
            return "confirmar_exclusao";
        }
    }

    @PostMapping("/alunos/excluir")
    public String excluirAluno(@ModelAttribute Aluno aluno) {
        alunoRepository.delete(aluno);
        return "redirect:/alunos";
    }
}
```

Isso permite que o usuário confirme a exclusão e, em seguida, o aluno é excluído do banco de dados.

Lembre-se de adicionar tratamento de erros e lidar com casos em que o aluno não é encontrado ou outros problemas que possam surgir durante a edição e exclusão de alunos.

Com esses métodos implementados, você pode criar uma aplicação Spring Boot que permite editar e excluir alunos do banco de dados. Certifique-se de criar as páginas HTML correspondentes e ajustar as URLs e os modelos para se adequarem ao seu projeto específico.