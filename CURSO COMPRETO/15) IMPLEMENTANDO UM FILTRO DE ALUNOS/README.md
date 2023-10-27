# IMPLEMENTANDO UM FILTRO DE ALUNOS
Um filtro de alunos é uma funcionalidade comum em muitos aplicativos para permitir que os usuários pesquisem e filtrem alunos com base em critérios específicos. Para implementar um filtro de alunos em um aplicativo Spring Boot, você pode seguir os passos abaixo:

**Passo 1: Criar uma Página para Exibir a Lista de Alunos**

Antes de implementar o filtro, é necessário ter uma página que exiba a lista de alunos. Isso pode ser feito seguindo os passos que foram mencionados anteriormente no curso.

**Passo 2: Criar o Formulário de Filtro**

Crie um formulário HTML que permita aos usuários inserir os critérios de filtro. Você pode criar uma página chamada `filtro_alunos.html` e adicionar campos de entrada para os critérios de filtro, como nome, idade, curso, etc.

```html
<form th:action="@{/alunos/filtrar}" method="post">
    <div class="form-group">
        <label for="nome">Nome</label>
        <input type="text" class="form-control" id="nome" name="nome" />
    </div>
    <div class="form-group">
        <label for="idade">Idade</label>
        <input type="number" class="form-control" id="idade" name="idade" />
    </div>
    <!-- Outros critérios de filtro -->
    <button type="submit" class="btn btn-primary">Filtrar</button>
</form>
```

**Passo 3: Criar um Controlador para Processar o Filtro**

Crie um controlador que processe o formulário de filtro e retorne a lista de alunos correspondente aos critérios. Você pode usar a anotação `@RequestParam` para receber os critérios de filtro e consultar o banco de dados para obter os resultados.

```java
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.ui.Model;

@Controller
public class FiltroAlunosController {

    @Autowired
    private AlunoRepository alunoRepository;

    @PostMapping("/alunos/filtrar")
    public String filtrarAlunos(
        @RequestParam("nome") String nome,
        @RequestParam("idade") Integer idade,
        Model model) {
        List<Aluno> alunosFiltrados = alunoRepository.filtrarAlunos(nome, idade);
        model.addAttribute("alunos", alunosFiltrados);
        return "lista_alunos";
    }
}
```

Neste exemplo, o método `filtrarAlunos` recebe os critérios de filtro (nome e idade) e consulta o banco de dados com base nesses critérios. Em seguida, os resultados são adicionados ao modelo e exibidos na página `lista_alunos`.

**Passo 4: Criar a Consulta no Repositório**

Adicione a consulta ao repositório `AlunoRepository` para filtrar os alunos com base nos critérios. Você pode usar o mecanismo de consulta do Spring Data JPA para criar consultas personalizadas.

```java
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.data.jpa.repository.Query;
import org.springframework.data.repository.query.Param;

public interface AlunoRepository extends JpaRepository<Aluno, Long> {
    
    @Query("SELECT a FROM Aluno a WHERE (:nome IS NULL OR a.nome LIKE %:nome%) AND (:idade IS NULL OR a.idade = :idade)")
    List<Aluno> filtrarAlunos(@Param("nome") String nome, @Param("idade") Integer idade);
}
```

Esta consulta permite filtrar alunos com base no nome (parcial) e idade. Se o usuário não inserir nenhum critério (por exemplo, deixar o campo de nome em branco), todos os alunos serão retornados.

**Passo 5: Exibir Resultados na Página**

Finalmente, na página `lista_alunos.html`, você pode exibir os resultados do filtro, da mesma forma que exibe a lista de alunos. Certifique-se de que o modelo seja atualizado corretamente com os resultados do filtro.

Agora, você implementou um filtro de alunos em seu aplicativo Spring Boot, permitindo que os usuários pesquisem e filtrem alunos com base em critérios específicos. Certifique-se de ajustar os campos de filtro e a consulta de acordo com as necessidades do seu aplicativo.