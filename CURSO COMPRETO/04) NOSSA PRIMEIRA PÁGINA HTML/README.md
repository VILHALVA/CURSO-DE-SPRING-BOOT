# NOSSA PRIMEIRA PÁGINA HTML
Se você está fazendo um curso de Spring Boot e deseja criar sua primeira página web usando o Spring Boot, é possível criar uma página HTML simples em um aplicativo Spring Boot. Vou guiá-lo nesse processo:

**Passo 1: Criar um Projeto Spring Boot**

1. Se você ainda não tiver um projeto Spring Boot, siga as etapas que mencionei anteriormente para criar um projeto Spring Boot usando o Spring Initializr. Certifique-se de incluir a dependência "Spring Web" para habilitar o suporte à criação de páginas web.

**Passo 2: Criar uma Página HTML**

2. Dentro do diretório do seu projeto, crie uma pasta chamada "resources" no diretório "src/main" se ela ainda não existir. Dentro da pasta "resources", crie outra pasta chamada "templates". Este é o local onde os modelos de suas páginas web serão armazenados.

3. Dentro da pasta "templates", crie um arquivo HTML. Por exemplo, você pode nomeá-lo "primeira_pagina.html" e, em seguida, adicione o seguinte conteúdo à página:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Minha Primeira Página com Spring Boot</title>
</head>
<body>
    <h1>Bem-vindo à Minha Primeira Página com Spring Boot</h1>
    <p>Esta é uma página HTML simples criada com Spring Boot.</p>
</body>
</html>
```

**Passo 3: Criar um Controlador**

4. Agora, você precisa criar um controlador Spring Boot para mapear a página HTML. Crie uma classe Java em seu projeto com uma anotação `@Controller` e um método que retorna o nome do arquivo HTML (sem a extensão ".html") como uma String. Por exemplo:

```java
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class MinhaPaginaController {
    @GetMapping("/primeira_pagina")
    public String primeiraPagina() {
        return "primeira_pagina";
    }
}
```

Neste exemplo, o método `primeiraPagina()` mapeia a URL "/primeira_pagina" para a página HTML "primeira_pagina.html".

**Passo 4: Executar o Aplicativo**

5. Execute o aplicativo Spring Boot. Você pode fazer isso a partir da sua IDE ou usando a linha de comando. Certifique-se de que o aplicativo esteja em execução.

**Passo 5: Acesse a Página**

6. Abra um navegador da web e acesse a URL "http://localhost:8080/primeira_pagina". Você verá a página HTML que você criou, com o título e o conteúdo que definiu.

Agora você tem sua primeira página HTML incorporada em um aplicativo Spring Boot. Isso é um exemplo básico, e o Spring Boot oferece muitas possibilidades para desenvolver aplicativos web mais complexos à medida que você avança em seu curso.