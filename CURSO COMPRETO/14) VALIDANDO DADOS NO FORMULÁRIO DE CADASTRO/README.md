# VALIDANDO DADOS NO FORMULÁRIO DE CADASTRO
Validar dados em um formulário de cadastro é uma prática importante para garantir a integridade e a qualidade dos dados inseridos em seu aplicativo Spring Boot. A validação de dados ajuda a evitar erros e problemas no banco de dados. Vou mostrar como você pode validar dados em um formulário de cadastro.

**Passo 1: Adicionar Dependências**

Certifique-se de que seu projeto Spring Boot tenha as dependências necessárias para a validação de dados. O Spring Boot fornece suporte à validação de dados por meio da especificação Bean Validation (JSR-303/JSR-349) e da implementação do Hibernate Validator. Certifique-se de que a dependência do Hibernate Validator esteja no seu arquivo `pom.xml`:

```xml
<dependency>
    <groupId>org.hibernate.validator</groupId>
    <artifactId>hibernate-validator</artifactId>
</dependency>
```

**Passo 2: Anotar a Classe do Modelo**

Anote a classe do modelo que representa os dados do formulário com as anotações de validação fornecidas pelo Hibernate Validator. Por exemplo, você pode adicionar anotações como `@NotNull`, `@Size`, `@Email`, `@Min`, `@Max`, entre outras, dependendo dos requisitos do seu aplicativo. Aqui está um exemplo:

```java
import javax.validation.constraints.NotBlank;
import javax.validation.constraints.NotNull;
import javax.validation.constraints.Size;

public class Aluno {
    @NotNull
    @NotBlank
    @Size(min = 3, max = 50)
    private String nome;

    @NotNull
    @Size(min = 18, max = 99)
    private int idade;

    // Outros campos e métodos
}
```

Neste exemplo, estamos usando anotações como `@NotNull` para garantir que os campos não sejam nulos, `@NotBlank` para garantir que os campos de texto não estejam em branco, `@Size` para definir limites no tamanho dos campos e `@Min` e `@Max` para definir limites em números inteiros.

**Passo 3: Configurar as Mensagens de Erro**

Você pode personalizar as mensagens de erro que serão exibidas quando a validação falhar. Para fazer isso, crie um arquivo `messages.properties` no diretório `src/main/resources` e adicione as mensagens personalizadas:

```properties
javax.validation.constraints.NotNull.message=Este campo não pode ser nulo.
javax.validation.constraints.NotBlank.message=Este campo não pode estar em branco.
javax.validation.constraints.Size.message=O tamanho do campo deve estar entre {min} e {max}.
javax.validation.constraints.Min.message=O valor deve ser maior ou igual a {value}.
javax.validation.constraints.Max.message=O valor deve ser menor ou igual a {value}.
```

**Passo 4: Validar no Controlador**

No controlador que lida com o processamento do formulário de cadastro, adicione um parâmetro de `BindingResult` após o objeto do modelo para capturar os erros de validação. Verifique se há erros e, se houver, redirecione o usuário de volta ao formulário de cadastro com as mensagens de erro apropriadas. Aqui está um exemplo:

```java
import org.springframework.validation.BindingResult;

@Controller
public class CadastroController {

    @Autowired
    private AlunoService alunoService;

    @PostMapping("/cadastro")
    public String processarFormulario(@Valid Aluno aluno, BindingResult bindingResult) {
        if (bindingResult.hasErrors()) {
            return "formulario_cadastro";
        }

        alunoService.salvarAluno(aluno);
        return "redirect:/sucesso";
    }
}
```

Neste exemplo, estamos usando a anotação `@Valid` para ativar a validação do modelo. Se ocorrerem erros de validação, o usuário será redirecionado de volta ao formulário de cadastro.

**Passo 5: Exibir Erros no Formulário**

No formulário de cadastro, você pode exibir as mensagens de erro nas posições apropriadas. Use a tag Thymeleaf `th:errors` para mostrar as mensagens de erro associadas a cada campo. Por exemplo:

```html
<form th:action="@{/cadastro}" method="post">
    <div class="form-group">
        <label for="nome">Nome</label>
        <input type="text" class="form-control" id="nome" name="nome" th:field="*{nome}">
        <small class="text-danger" th:errors="*{nome}"></small>
    </div>
    <div class="form-group">
        <label for="idade">Idade</label>
        <input type="number" class="form-control" id="idade" name="idade" th:field="*{idade}">
        <small class="text-danger" th:errors="*{idade}"></small>
    </div>
    <button type="submit" class="btn btn-primary">Cadastrar</button>
</form>
```

Neste exemplo, usamos `th:errors` para exibir as mensagens de erro associadas aos campos "nome" e "idade".

Agora, o seu formulário de cadastro estará configurado para validar os dados de entrada e exibir mensagens de erro quando necessário. Certifique-se de ajustar as anotações de validação e as mensagens de erro de acordo com os requisitos do seu aplicativo.