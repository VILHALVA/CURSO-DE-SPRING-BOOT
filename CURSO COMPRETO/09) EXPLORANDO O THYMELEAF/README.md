# EXPLORANDO O THYMELEAF
O Thymeleaf é um mecanismo de modelo para criar páginas da web em aplicativos Spring Boot. Ele é amplamente utilizado e permite a criação de páginas web dinâmicas, com suporte para a integração de dados do servidor em suas páginas HTML. Vou guiá-lo na exploração do Thymeleaf em um projeto Spring Boot:

**Passo 1: Configurar o Projeto**

Certifique-se de que você já tenha um projeto Spring Boot configurado. O Thymeleaf é frequentemente incluído como uma dependência padrão nos projetos Spring Boot, mas você pode verificar o seu arquivo `pom.xml` para confirmar a presença da dependência do Thymeleaf.

**Passo 2: Estrutura de Diretórios**

No projeto Spring Boot, é comum organizar seus modelos Thymeleaf na pasta `src/main/resources/templates`. Certifique-se de que esta pasta exista.

**Passo 3: Criar um Modelo Thymeleaf**

1. Crie um novo arquivo HTML na pasta `src/main/resources/templates`. Por exemplo, você pode criar um arquivo chamado `exemplo.html`.

2. Em seu arquivo HTML, você pode usar tags Thymeleaf para incluir variáveis, expressões e loops de controle. Por exemplo, você pode usar `${...}` para incluir variáveis e `th:each` para loops. Aqui está um exemplo simples:

```html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Exemplo Thymeleaf</title>
</head>
<body>
    <h1>Olá, <span th:text="${nome}">Visitante</span>!</h1>
    
    <ul>
        <li th:each="fruta : ${frutas}" th:text="${fruta}">Maçã</li>
    </ul>
</body>
</html>
```

Neste exemplo, estamos usando `th:text` para exibir o valor da variável `nome` e `th:each` para iterar sobre a lista de `frutas`.

**Passo 4: Criar um Controlador Spring Boot**

1. Crie um controlador Spring Boot que manipulará a solicitação para a página do modelo Thymeleaf. Por exemplo:

```java
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

import java.util.Arrays;
import java.util.List;

@Controller
public class ExemploController {
    @GetMapping("/exemplo")
    public String exemplo(Model model) {
        model.addAttribute("nome", "Usuário");
        List<String> frutas = Arrays.asList("Maçã", "Banana", "Laranja");
        model.addAttribute("frutas", frutas);
        return "exemplo";
    }
}
```

Neste exemplo, o controlador mapeia a URL `/exemplo` para o modelo Thymeleaf `exemplo.html`. Ele também define as variáveis `nome` e `frutas` que serão usadas no modelo.

**Passo 5: Acessar o Modelo Thymeleaf**

1. Inicie ou reinicie seu aplicativo Spring Boot.

2. Acesse a URL correspondente ao modelo Thymeleaf. Neste caso, acesse `http://localhost:8080/exemplo` em um navegador da web.

Você verá a página com o modelo Thymeleaf renderizado, exibindo o nome e a lista de frutas. O Thymeleaf permite que você integre facilmente dados do servidor em suas páginas web e crie páginas dinâmicas de maneira conveniente.

Este é um exemplo básico de como usar o Thymeleaf em um projeto Spring Boot. À medida que você avança em seu projeto, você pode explorar recursos mais avançados, como formatação de datas, internacionalização e muito mais.