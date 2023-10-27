# IMPLEMENTANDO PESQUISA DE ALUNOS FÁCIL E RÁPIDO
Para implementar uma pesquisa de alunos rápida e fácil em um aplicativo Spring Boot, você pode usar recursos do Spring Data JPA, que simplificam a criação de consultas personalizadas no banco de dados. Aqui estão os passos para realizar essa implementação:

**Passo 1: Criar um Controlador e uma Página de Pesquisa**

Crie um controlador para lidar com a pesquisa de alunos e uma página HTML para exibir os resultados. Por exemplo, você pode criar um controlador chamado `PesquisaAlunosController` e uma página chamada `pesquisa_alunos.html`.

**Passo 2: Adicionar um Campo de Entrada de Pesquisa na Página**

Na página `pesquisa_alunos.html`, adicione um campo de entrada onde os usuários possam inserir os critérios de pesquisa, como nome, idade, curso, etc. Além disso, adicione um botão "Pesquisar" para acionar a pesquisa.

```html
<form th:action="@{/alunos/pesquisar}" method="get">
    <div class="form-group">
        <label for="termo">Termo de pesquisa</label>
        <input type="text" class="form-control" id="termo" name="termo" />
    </div>
    <button type="submit" class="btn btn-primary">Pesquisar</button>
</form>
```

**Passo 3: Criar um Método no Controlador para Processar a Pesquisa**

No controlador `PesquisaAlunosController`, crie um método que processa a pesquisa com base no termo inserido pelo usuário.

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.ui.Model;

@Controller
public class PesquisaAlunosController {

    @Autowired
    private AlunoRepository alunoRepository;

    @GetMapping("/alunos/pesquisar")
    public String pesquisarAlunos(@RequestParam("termo") String termo, Model model) {
        List<Aluno> alunosEncontrados = alunoRepository.findByNomeContainingIgnoreCaseOrCursoContainingIgnoreCase(termo, termo);
        model.addAttribute("alunos", alunosEncontrados);
        return "pesquisa_alunos";
    }
}
```

Neste exemplo, o método `pesquisarAlunos` usa a consulta gerada automaticamente pelo Spring Data JPA para encontrar alunos cujo nome ou curso contenha o termo de pesquisa, ignorando maiúsculas e minúsculas.

**Passo 4: Exibir os Resultados na Página de Pesquisa**

Na página `pesquisa_alunos.html`, você pode exibir os resultados da pesquisa da mesma forma que exibe a lista de alunos. Certifique-se de que o modelo seja atualizado corretamente com os resultados da pesquisa.

**Passo 5: Testar a Pesquisa**

Inicie ou reinicie seu aplicativo Spring Boot e acesse a página de pesquisa de alunos. Insira um termo de pesquisa e clique em "Pesquisar" para ver os resultados.

Com esses passos, você implementou uma pesquisa de alunos rápida e fácil em seu aplicativo Spring Boot. O Spring Data JPA simplifica a criação de consultas personalizadas e facilita a implementação de recursos de pesquisa. Certifique-se de ajustar os campos de pesquisa e a consulta de acordo com as necessidades do seu aplicativo.