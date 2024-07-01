# INSTRUÇÕES
## 01) CONHECENDO O SPRING
A introdução, instalação e configuração do Spring Boot são etapas cruciais para começar a desenvolver aplicativos com sucesso. Vou guiá-lo através desses processos.

**Introdução ao Spring Boot:**

O Spring Boot é uma estrutura Java que simplifica o desenvolvimento de aplicativos, proporcionando uma configuração fácil e conveniente. Ele é baseado no Spring Framework e é projetado para criar aplicativos rapidamente, com o mínimo de configuração. O Spring Boot fornece uma variedade de recursos, incluindo injeção de dependência, autoconfiguração, servidores incorporados e muito mais.

**Instalação do Spring Boot:**

Para começar com o Spring Boot, você precisará instalar o Java Development Kit (JDK) em seu sistema. O Spring Boot é compatível com várias versões do JDK, geralmente JDK 8, 11 ou 17. Aqui estão os passos para instalar o Spring Boot:

1. **Instale o JDK:** Se você ainda não tiver o JDK instalado, faça o download e siga as instruções para a instalação no site oficial da Oracle ou de uma distribuição OpenJDK.

2. **Configuração do Ambiente:** Certifique-se de que a variável de ambiente `JAVA_HOME` esteja configurada corretamente para apontar para a pasta de instalação do JDK.

3. **Instale o Spring Boot CLI (Opcional):** O Spring Boot oferece uma CLI que facilita a criação rápida de projetos. Você pode instalá-lo seguindo as instruções no site oficial do Spring Boot.

4. **Escolha uma IDE:** Você pode usar uma IDE como o Spring Tool Suite (STS), IntelliJ IDEA ou Eclipse para desenvolver aplicativos Spring Boot. Essas IDEs oferecem suporte aprimorado para desenvolvimento Spring.

**Configuração Inicial do Spring Boot:**

A configuração inicial de um projeto Spring Boot é simplificada usando o Spring Initializr, uma ferramenta on-line que gera esqueletos de projeto Spring Boot com base nas dependências e configurações que você escolher. Aqui estão os passos:

1. Acesse [Spring Initializr](https://start.spring.io/) em seu navegador.

2. Escolha as configurações do projeto, como o tipo de projeto (Maven ou Gradle), a versão do Spring Boot, as dependências (por exemplo, Spring Web, Spring Data JPA) e o idioma (Java, Kotlin).

3. Clique no botão "Generate" para baixar o arquivo ZIP do projeto gerado.

4. Descompacte o arquivo ZIP em um diretório de sua escolha.

5. Abra o projeto em sua IDE e comece a escrever código.

A partir deste ponto, você pode começar a desenvolver seu aplicativo Spring Boot. O Spring Boot oferece muitas facilidades para configurar suas classes, injeção de dependência, mapeamento de URLs e muito mais.

Lembre-se de que a configuração adicional pode ser feita no arquivo de propriedades `application.properties` ou `application.yml` para personalizar as configurações do aplicativo, como configurações de banco de dados e propriedades específicas do aplicativo.

## 02) ARQUITETURA MVC
A arquitetura MVC (Model-View-Controller) é um padrão de design amplamente utilizado em desenvolvimento de software para separar os componentes de um aplicativo em três partes distintas: Model, View e Controller. O objetivo principal do padrão MVC é melhorar a modularidade, a manutenção e a escalabilidade de aplicativos, permitindo que cada componente cumpra uma função específica. Aqui está uma explicação de cada um dos componentes:

1. **Model (Modelo):**
   
   O componente Model representa a camada de dados do aplicativo. Ele lida com a lógica de negócios, a manipulação de dados e a comunicação com o banco de dados. O Model é responsável por armazenar e recuperar informações do aplicativo. Ele não está ciente da interface do usuário ou de como os dados são apresentados.

2. **View (Visão):**
   
   O componente View é responsável pela interface do usuário. Ele lida com a apresentação dos dados ao usuário. A View exibe informações do Modelo de forma atraente e interativa. Geralmente, inclui elementos como páginas da web, interfaces gráficas de usuário (GUIs), telas de dispositivos móveis e outros meios de exibição.

3. **Controller (Controlador):**
   
   O componente Controller atua como um intermediário entre o Modelo e a View. Ele recebe as solicitações do usuário, processa-as, interage com o Modelo para obter ou atualizar dados e, em seguida, atualiza a View para refletir as mudanças. O Controller gerencia a lógica de fluxo de controle e é responsável por garantir que as ações do usuário sejam refletidas no Modelo e na View apropriados.

A principal vantagem da arquitetura MVC é a separação de responsabilidades. Isso torna o código mais modular, facilitando a manutenção, a escalabilidade e o trabalho em equipe. Por exemplo, você pode fazer alterações na interface do usuário (View) sem afetar a lógica de negócios (Model) subjacente. Da mesma forma, o Modelo pode ser modificado sem afetar a View.

No contexto de um aplicativo Spring Boot, o Spring Framework facilita a implementação da arquitetura MVC. Aqui estão algumas das principais classes e componentes que você pode encontrar em um aplicativo Spring Boot baseado em MVC:

- **Controller (Controlador):** Classes anotadas com `@Controller` são responsáveis por lidar com as solicitações HTTP, chamando métodos nos Modelos apropriados e atualizando as Views correspondentes. 

- **Model (Modelo):** Classes que representam o Modelo de negócios do aplicativo, geralmente anotadas com `@Entity` para persistência em banco de dados, e podem conter métodos de lógica de negócios.

- **View (Visão):** Pode ser implementada usando templates HTML, páginas JSP, ou qualquer outro mecanismo de visualização, dependendo das tecnologias escolhidas no projeto.

No Spring Boot, a configuração inicial para um aplicativo baseado em MVC é simplificada, e você pode começar rapidamente a criar aplicativos web que seguem o padrão MVC.

## 03) INICIANDO NOSSO PROJETO
Iniciar um projeto Spring Boot é um processo relativamente simples, especialmente com a ajuda do Spring Initializr, uma ferramenta on-line que gera o esqueleto de um projeto Spring Boot com base nas suas preferências. Vou guiá-lo pelo processo de iniciar um novo projeto Spring Boot:

**Passo 1: Acesse o Spring Initializr**

1. Abra o seu navegador da web e acesse [https://start.spring.io/](https://start.spring.io/).

**Passo 2: Configure o Projeto**

2. No Spring Initializr, você verá várias opções para configurar o seu projeto. Aqui estão as configurações comuns que você pode ajustar:

   - **Project:** Escolha "Maven" ou "Gradle" com base na sua preferência para a ferramenta de gerenciamento de build.

   - **Language:** Escolha "Java" ou "Kotlin" como a linguagem de programação principal.

   - **Spring Boot:** Selecione a versão do Spring Boot que você deseja usar. A versão mais recente é geralmente a melhor escolha, a menos que você tenha requisitos específicos.

   - **Project Metadata:** Preencha os campos, como o nome do grupo, o nome do artefato (nome do projeto) e o pacote base da aplicação.

   - **Packaging:** Escolha "Jar" para criar um arquivo JAR executável ou "War" se você planeja implantar o aplicativo em um servidor de aplicativos.

   - **Java:** Escolha a versão do JDK que você está usando.

   - **Dependencies:** Esta é uma parte importante. Aqui você pode selecionar as dependências específicas que seu projeto precisa. Por exemplo, se você estiver criando um aplicativo da web, selecione "Spring Web". Se você precisar de acesso a banco de dados, escolha "Spring Data JPA" e a biblioteca de banco de dados desejada (por exemplo, H2, MySQL, PostgreSQL).

**Passo 3: Gerar o Projeto**

3. Após configurar todas as opções de acordo com suas necessidades, clique no botão "Generate" para gerar o projeto. Isso fará o download de um arquivo ZIP contendo o esqueleto do seu projeto Spring Boot.

**Passo 4: Descompactar e Importar o Projeto**

4. Descompacte o arquivo ZIP baixado em um diretório de sua escolha. Em seguida, abra a sua IDE (como o Spring Tool Suite, IntelliJ IDEA ou Eclipse) e importe o projeto como um projeto Maven ou Gradle, dependendo da sua escolha anterior.

**Passo 5: Comece a Codificar**

5. Com o projeto importado em sua IDE, você está pronto para começar a codificar. O Spring Boot já configurou a estrutura básica do projeto, incluindo a classe principal com o método `main()` que inicia o aplicativo. Você pode começar a criar controladores, modelos e visualizações de acordo com a arquitetura MVC ou suas necessidades específicas.

Lembre-se de que você pode personalizar a configuração do projeto posteriormente, adicionando dependências adicionais no arquivo de configuração do Maven ou Gradle e ajustando as propriedades de configuração no arquivo `application.properties` ou `application.yml`.

Esse é um guia básico para iniciar um projeto Spring Boot. À medida que você avança no desenvolvimento, pode se aprofundar nos recursos e funcionalidades oferecidos pelo Spring Boot para atender às necessidades específicas do seu aplicativo.

## 04) NOSSA PRIMEIRA PÁGINA HTML
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

## 05) UTILIZANDO BIBLIOTECA WEBJARS NO PROJETO
Utilizar a biblioteca WebJars em um projeto Spring Boot é uma ótima maneira de incorporar recursos da web, como bibliotecas JavaScript e CSS, diretamente em seu aplicativo. Isso facilita a gestão de dependências de recursos da web, como jQuery, Bootstrap, FontAwesome e muitos outros, utilizando o sistema de gerenciamento de dependências do Spring Boot.

Aqui está um guia passo a passo sobre como utilizar a biblioteca WebJars em um projeto Spring Boot:

**Passo 1: Adicionar Dependência WebJars**

1. Abra o arquivo `pom.xml` (se você estiver usando o Maven) em seu projeto Spring Boot.

2. Adicione a dependência WebJars que corresponde à biblioteca que você deseja usar. Por exemplo, se você deseja adicionar o jQuery, adicione a dependência da seguinte forma:

   ```xml
   <dependency>
       <groupId>org.webjars</groupId>
       <artifactId>jquery</artifactId>
       <version>3.6.0</version> <!-- Versão do jQuery -->
   </dependency>
   ```

   Certifique-se de substituir a versão pelo número da versão desejada.

3. Salve o arquivo `pom.xml` para que as alterações sejam aplicadas.

**Passo 2: Configurar Recursos Estáticos**

1. Por padrão, o Spring Boot serve recursos estáticos (JavaScript, CSS, etc.) da pasta `src/main/resources/static`. Certifique-se de que a pasta `static` existe no diretório `resources`. Se não existir, crie-a.

**Passo 3: Usar Recursos WebJars em HTML**

1. Em seu arquivo HTML, você pode incluir recursos WebJars diretamente usando o caminho definido no WebJars. Por exemplo, para incluir o jQuery, você pode fazer o seguinte:

   ```html
   <script src="/webjars/jquery/3.6.0/jquery.min.js"></script>
   ```

   Observe que o caminho inclui `/webjars/nome-da-biblioteca/versao/caminho-para-o-recurso`.

**Passo 4: Inicializar o Aplicativo**

1. Inicie ou reinicie seu aplicativo Spring Boot para garantir que as alterações na configuração sejam aplicadas.

**Passo 5: Testar e Usar os Recursos WebJars**

1. Acesse a página em que você incluiu recursos WebJars no navegador. Os recursos, como jQuery, devem ser carregados a partir do caminho definido na etapa anterior.

Isso é tudo o que você precisa fazer para adicionar e usar bibliotecas WebJars em um projeto Spring Boot. Lembre-se de que você pode adicionar mais bibliotecas WebJars seguindo os mesmos passos, apenas adicionando as dependências correspondentes em seu arquivo `pom.xml` e usando o caminho correto nos seus arquivos HTML.

## 06) CRIANDO MENU DE NAVEGAÇÃO COM BOOTSTRAP
Criar um menu de navegação com Bootstrap em um aplicativo Spring Boot é uma ótima maneira de adicionar uma barra de navegação responsiva e visualmente atraente ao seu aplicativo web. O Bootstrap é uma estrutura de front-end que facilita a criação de menus de navegação elegantes e compatíveis com dispositivos móveis.

Aqui estão os passos para criar um menu de navegação com Bootstrap em um projeto Spring Boot:

**Passo 1: Configurar o Projeto Spring Boot**

Certifique-se de que você tenha um projeto Spring Boot configurado e funcional. Você pode criar um novo projeto Spring Boot com o Spring Initializr ou usar um projeto existente.

**Passo 2: Adicionar Bootstrap ao Projeto**

1. Abra o arquivo `pom.xml` em seu projeto Spring Boot.

2. Adicione a dependência do Bootstrap. Você pode fazer isso incluindo o seguinte trecho em seu arquivo `pom.xml`:

   ```xml
   <dependency>
       <groupId>org.webjars</groupId>
       <artifactId>bootstrap</artifactId>
       <version>5.0.0</version> <!-- Substitua pela versão mais recente do Bootstrap -->
   </dependency>
   ```

   Lembre-se de atualizar a versão para a versão mais recente do Bootstrap, se necessário.

3. Salve o arquivo `pom.xml`.

**Passo 3: Criar um Menu de Navegação com Bootstrap**

1. Crie uma nova página HTML (por exemplo, `menu.html`) na pasta `src/main/resources/templates` do seu projeto Spring Boot.

2. No arquivo `menu.html`, adicione o código HTML para criar o menu de navegação com Bootstrap. Aqui está um exemplo básico de um menu de navegação:

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Menu de Navegação com Bootstrap</title>
       <!-- Adicione a referência ao Bootstrap CSS -->
       <link href="/webjars/bootstrap/5.0.0/dist/css/bootstrap.min.css" rel="stylesheet">
   </head>
   <body>
       <nav class="navbar navbar-expand-lg navbar-light bg-light">
           <a class="navbar-brand" href="#">Meu Site</a>
           <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
               <span class="navbar-toggler-icon"></span>
           </button>
           <div class="collapse navbar-collapse" id="navbarNav">
               <ul class="navbar-nav">
                   <li class="nav-item active">
                       <a class="nav-link" href="/">Página Inicial</a>
                   </li>
                   <li class="nav-item">
                       <a class="nav-link" href="/sobre">Sobre</a>
                   </li>
                   <li class="nav-item">
                       <a class="nav-link" href="/contato">Contato</a>
                   </li>
               </ul>
           </div>
       </nav>

       <!-- Adicione a referência ao Bootstrap JavaScript e ao jQuery (obrigatório para Bootstrap) -->
       <script src="/webjars/jquery/3.6.0/jquery.min.js"></script>
       <script src="/webjars/bootstrap/5.0.0/dist/js/bootstrap.min.js"></script>
   </body>
   </html>
   ```

   Neste exemplo, temos um menu de navegação responsivo com três links: "Página Inicial", "Sobre" e "Contato". Certifique-se de substituir os URLs (`href`) pelos URLs correspondentes das páginas do seu aplicativo Spring Boot.

**Passo 4: Acessar o Menu de Navegação**

1. Inicie ou reinicie seu aplicativo Spring Boot para que as alterações na configuração sejam aplicadas.

2. Acesse a página do menu de navegação em um navegador da web, utilizando o caminho correspondente (por exemplo, "http://localhost:8080/menu").

Você deverá ver o menu de navegação Bootstrap funcionando, proporcionando uma barra de navegação responsiva e elegante para o seu aplicativo Spring Boot. Você pode personalizar o menu e adicionar mais funcionalidades à medida que seu projeto se desenvolve.

## 07) FINALIZANDO NOSSA PÁGINA PRINCIPAL
Finalizar a página principal de um aplicativo Spring Boot envolve adicionar conteúdo, estilos e possivelmente interatividade, dependendo dos requisitos do seu projeto. Vou fornecer um exemplo simples de como você pode finalizar a página principal, mas lembre-se de que a complexidade e o estilo dependerão do que você deseja realizar.

**Passo 1: Estrutura da Página HTML**

A primeira etapa é a estrutura da página HTML. Você pode adicionar conteúdo e estilização de acordo com suas necessidades. Aqui está um exemplo básico de uma página HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minha Página Inicial</title>
    <!-- Inclua links para estilos CSS, se aplicável -->
</head>
<body>
    <header>
        <nav>
            <!-- Adicione um menu de navegação se necessário -->
        </nav>
    </header>

    <main>
        <h1>Bem-vindo à Minha Página Inicial</h1>
        <p>Esta é a página principal do meu aplicativo Spring Boot.</p>
        <!-- Adicione mais conteúdo aqui, como imagens, parágrafos, formulários, etc. -->
    </main>

    <footer>
        <p>&copy; 2023 Meu Aplicativo Spring Boot</p>
    </footer>
</body>
</html>
```

**Passo 2: Estilos CSS (Opcional)**

Se desejar estilizar a página, você pode incluir um arquivo CSS externo ou estilos internos no cabeçalho do HTML. Aqui está um exemplo simples com estilos internos:

```html
<head>
    <!-- ... outras meta tags ... -->
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
        }
        header {
            background-color: #333;
            color: #fff;
            padding: 10px;
        }
        h1 {
            color: #333;
        }
        /* Adicione mais estilos personalizados aqui */
    </style>
</head>
```

**Passo 3: Adicionar Interatividade (Opcional)**

Se desejar tornar sua página inicial interativa, você pode adicionar scripts JavaScript. Por exemplo, pode criar formulários de contato, elementos de carrossel ou funcionalidades específicas do seu aplicativo.

**Passo 4: Testar e Refinar**

Após adicionar conteúdo, estilos e possivelmente interatividade, teste a página em seu navegador para garantir que tudo esteja funcionando conforme o esperado. Faça ajustes e refinamentos conforme necessário para atender aos requisitos do seu projeto.

**Passo 5: Integração com o Spring Boot**

Se você deseja incluir essa página principal em seu aplicativo Spring Boot, basta criar um controlador que mapeie a URL da página para um método que retorna o nome da página (sem a extensão ".html"). Por exemplo:

```java
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class PaginaPrincipalController {
    @GetMapping("/")
    public String paginaPrincipal() {
        return "pagina_principal";
    }
}
```

Isso faz com que a página seja acessível em "http://localhost:8080/" (ou o URL base do seu aplicativo Spring Boot).

Lembre-se de personalizar a página de acordo com os requisitos do seu projeto, adicionar estilos e interatividade, e testar exaustivamente para garantir que tudo funcione conforme o esperado.

## 08) RESPONSIVIDADE E AJUSTES FINAIS
Adicionar responsividade e fazer ajustes finais em um aplicativo Spring Boot envolve tornar seu site compatível com diversos dispositivos e tamanhos de tela, como desktops, tablets e smartphones. O Bootstrap é uma ótima ferramenta para criar layouts responsivos com facilidade. Aqui estão os passos para tornar sua página responsiva e realizar ajustes finais:

**Passo 1: Usar o Bootstrap**

1. Certifique-se de que você já incluiu o Bootstrap no seu projeto Spring Boot, conforme mencionado anteriormente. O Bootstrap oferece uma grade flexível e componentes responsivos que facilitam a criação de layouts que se adaptam a diferentes tamanhos de tela.

**Passo 2: Utilizar a Grade do Bootstrap**

2. A grade do Bootstrap é baseada em um sistema de 12 colunas. Ao usar a classe `col`, você pode especificar quantas colunas um elemento ocupará em diferentes tamanhos de tela (por exemplo, `col-md-6` para ocupar metade da largura em telas médias). Aqui está um exemplo de uso da grade:

```html
<div class="container">
    <div class="row">
        <div class="col-md-6">Conteúdo da Coluna 1</div>
        <div class="col-md-6">Conteúdo da Coluna 2</div>
    </div>
</div>
```

Isso cria duas colunas, cada uma ocupando metade da largura em telas médias e maiores.

**Passo 3: Testar em Diferentes Tamanhos de Tela**

3. Teste sua página em vários dispositivos e tamanhos de tela para garantir que o layout responda corretamente. Você pode redimensionar a janela do navegador para testar diferentes tamanhos ou usar ferramentas de desenvolvedor que emulam dispositivos móveis.

**Passo 4: Ajustes Finais de Estilo**

4. Faça ajustes de estilo para garantir que seu site seja visualmente atraente em diferentes tamanhos de tela. Isso pode incluir ajustes de tamanho de fonte, margens, cores e outros detalhes de design.

**Passo 5: Tratamento de Imagens e Mídias**

5. Ao exibir imagens ou mídias, certifique-se de que elas se redimensionem adequadamente para caber na tela. O Bootstrap oferece classes para garantir que as imagens se ajustem automaticamente.

```html
<img src="imagem.jpg" class="img-fluid" alt="Imagem Responsiva">
```

**Passo 6: Teste em Diferentes Navegadores**

6. Teste seu aplicativo em diferentes navegadores (como Chrome, Firefox, Safari, Edge) para garantir que ele funcione corretamente em todos eles. Considere a compatibilidade com navegadores mais antigos, se necessário.

**Passo 7: Documentação e Comentários**

7. Documente seu código e adicione comentários para facilitar a manutenção no futuro. Isso é especialmente importante se outras pessoas trabalharem no projeto.

**Passo 8: Validação e Testes**

8. Realize testes de validação e testes de unidade para garantir que seu aplicativo funcione conforme o esperado.

**Passo 9: Implementar SEO (Opcional)**

9. Se o seu site será público e visível nos mecanismos de busca, considere implementar práticas de otimização de mecanismos de busca (SEO) para melhorar sua visibilidade online.

Lembre-se de que a responsividade e os ajustes finais podem variar dependendo do tamanho e da complexidade do seu projeto. No entanto, seguir esses passos gerais ajudará a criar uma experiência de usuário consistente e agradável em uma variedade de dispositivos e navegadores.

## 09) EXPLORANDO O THYMELEAF
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

## 10) CONEXÃO COM O BANCO DE DADOS E CRIAÇÃO DA CLASSE ALUNO
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

## 11) INSERINDO DADOS NO BANCO COM JPA E HIBERNATE
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

## 12) LISTANDO OS ALUNOS DO BANCO DE DADOS
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

## 13) MÉTODO EDITAR E EXCLUIR ALUNO
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

## 14) VALIDANDO DADOS NO FORMULÁRIO DE CADASTRO
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

## 15) IMPLEMENTANDO UM FILTRO DE ALUNOS
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

## 16) IMPLEMENTANDO PESQUISA DE ALUNOS FÁCIL E RÁPIDO
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

## 17) LOGIN DO USUÁRIO
A implementação de um sistema de login de usuário em um aplicativo Spring Boot geralmente envolve uma série de etapas. Vou guiar você pelas principais etapas envolvidas na criação de um sistema de login simples.

**Passo 1: Criar a Entidade de Usuário**

Comece criando uma entidade de usuário que representará os detalhes do usuário no seu aplicativo. Aqui está um exemplo de uma entidade de usuário:

```java
@Entity
public class Usuario {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String nome;
    private String email;
    private String senha;

    // Getters e setters
}
```

Esta entidade contém campos como nome, email e senha. A senha deve ser armazenada de forma segura (por exemplo, com hash e salt) para garantir a segurança.

**Passo 2: Criar um Repositório de Usuário**

Crie um repositório para a entidade `Usuario` que permitirá a interação com o banco de dados para operações relacionadas a usuários.

```java
public interface UsuarioRepository extends JpaRepository<Usuario, Long> {
    Usuario findByEmail(String email);
}
```

Isso permite encontrar um usuário com base no email.

**Passo 3: Implementar a Autenticação**

O Spring Security é uma ferramenta popular para implementar a autenticação e autorização em aplicativos Spring Boot. Você pode adicioná-lo como dependência em seu arquivo `pom.xml`:

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-security</artifactId>
</dependency>
```

Em seguida, você pode configurar a segurança em seu aplicativo Spring Boot. Isso pode ser feito em uma classe de configuração:

```java
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder;
import org.springframework.security.crypto.password.PasswordEncoder;

@Configuration
@EnableWebSecurity
public class SecurityConfig extends WebSecurityConfigurerAdapter {

    @Autowired
    private UsuarioDetailsService usuarioDetailsService;

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http
            .authorizeRequests()
                .antMatchers("/public/**").permitAll()
                .anyRequest().authenticated()
                .and()
            .formLogin()
                .loginPage("/login")
                .permitAll()
                .and()
            .logout()
                .permitAll();
    }

    @Bean
    public PasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder();
    }

    @Autowired
    public void configureGlobal(AuthenticationManagerBuilder auth) throws Exception {
        auth.userDetailsService(usuarioDetailsService).passwordEncoder(passwordEncoder());
    }
}
```

Neste exemplo, a classe `SecurityConfig` estende `WebSecurityConfigurerAdapter` e configura a autenticação por meio do Spring Security. Ela define URLs públicas e a página de login. O `UsuarioDetailsService` é uma classe que implementa a interface `UserDetailsService` e é responsável por carregar os detalhes do usuário.

**Passo 4: Criar a Página de Login**

Crie uma página HTML para o formulário de login, geralmente chamada `login.html`. Esta página deve estar acessível a todos (não protegida) e conter um formulário onde os usuários possam inserir seu email e senha.

```html
<form th:action="@{/login}" method="post">
    <div class="form-group">
        <label for="email">Email</label>
        <input type="text" class="form-control" id="email" name="email" />
    </div>
    <div class="form-group">
        <label for="senha">Senha</label>
        <input type="password" class="form-control" id="senha" name="senha" />
    </div>
    <button type="submit" class="btn btn-primary">Login</button>
</form>
```

**Passo 5: Implementar a Lógica de Login**

Crie um controlador que processa a lógica de login e autenticação.

```java
@Controller
public class LoginController {

    @GetMapping("/login")
    public String login() {
        return "login";
    }
}
```

**Passo 6: Implementar o Serviço de Detalhes do Usuário**

Implemente o serviço que carrega os detalhes do usuário com base no email.

```java
@Service
public class UsuarioDetailsService implements UserDetailsService {

    @Autowired
    private UsuarioRepository usuarioRepository;

    @Override
    public UserDetails loadUserByUsername(String email) throws UsernameNotFoundException {
        Usuario usuario = usuarioRepository.findByEmail(email);
        if (usuario == null) {
            throw new UsernameNotFoundException("Usuário não encontrado");
        }
        return new User(usuario.getEmail(), usuario.getSenha(), Collections.emptyList());
    }
}
```

**Passo 7: Proteger Recursos Restritos**

Você pode usar anotações como `@PreAuthorize` para proteger recursos restritos em seu aplicativo. Por exemplo:

```java
@PreAuthorize("hasRole('ROLE_USER')")
@RequestMapping("/restrito")
public String recursoRestrito() {
    return "restrito";
}
```

Isso garante que apenas usuários autenticados tenham acesso a recursos restritos.

Com esses passos, você implementou um sistema de login de usuário básico em um aplicativo Spring Boot. Você pode aprimorá-lo adicionando recursos como registro de usuário, recuperação de senha, e gerenciamento de papéis e permissões, conforme necessário para atender aos requisitos do seu aplicativo.

## 18) CRIPTOGRAFIA E CAMADA SERVICE DO LOGIN
A criptografia e a camada de serviço no sistema de login são aspectos críticos para a segurança de um aplicativo Spring Boot. A criptografia é essencial para proteger as senhas dos usuários e garantir que elas não sejam armazenadas em texto simples no banco de dados. A camada de serviço é responsável por lidar com a lógica de negócios relacionada à autenticação e autorização. Vou explicar como implementar esses aspectos.

**Criptografia de Senha**

Para criptografar senhas no Spring Boot, você pode usar a biblioteca BCrypt. Siga os seguintes passos:

1. Adicione a dependência do BCrypt ao seu arquivo `pom.xml`:

```xml
<dependency>
    <groupId>org.springframework.security</groupId>
    <artifactId>spring-security-crypto</artifactId>
</dependency>
```

2. Na camada de serviço, onde você está processando o registro de novos usuários, utilize o BCrypt para criptografar a senha antes de armazená-la no banco de dados. Por exemplo:

```java
import org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder;

@Service
public class UsuarioService {

    @Autowired
    private UsuarioRepository usuarioRepository;

    @Autowired
    private BCryptPasswordEncoder passwordEncoder;

    public void registrarNovoUsuario(Usuario usuario) {
        String senhaCriptografada = passwordEncoder.encode(usuario.getSenha());
        usuario.setSenha(senhaCriptografada);
        usuarioRepository.save(usuario);
    }
}
```

3. Certifique-se de configurar o `BCryptPasswordEncoder` na sua classe de configuração de segurança, como mostrado no exemplo anterior.

**Camada de Serviço do Login**

A camada de serviço é responsável por realizar a autenticação de usuários e carregar seus detalhes. Você pode criar um serviço personalizado para isso. Aqui estão os passos:

1. Crie uma classe de serviço para gerenciar a autenticação:

```java
@Service
public class UsuarioDetailsService implements UserDetailsService {

    @Autowired
    private UsuarioRepository usuarioRepository;

    @Override
    public UserDetails loadUserByUsername(String email) throws UsernameNotFoundException {
        Usuario usuario = usuarioRepository.findByEmail(email);
        if (usuario == null) {
            throw new UsernameNotFoundException("Usuário não encontrado");
        }
        return new User(usuario.getEmail(), usuario.getSenha(), Collections.emptyList());
    }
}
```

2. No seu controlador de login, você pode usar o `AuthenticationManager` para realizar a autenticação. Aqui está um exemplo:

```java
import org.springframework.security.core.Authentication;
import org.springframework.security.core.AuthenticationException;
import org.springframework.security.authentication.AuthenticationManager;

@Controller
public class LoginController {

    @Autowired
    private AuthenticationManager authenticationManager;

    @Autowired
    private UsuarioDetailsService usuarioDetailsService;

    @GetMapping("/login")
    public String login() {
        return "login";
    }

    @PostMapping("/login")
    public String realizarLogin(@RequestParam String email, @RequestParam String senha) {
        UsernamePasswordAuthenticationToken token = new UsernamePasswordAuthenticationToken(email, senha);
        Authentication authentication = authenticationManager.authenticate(token);
        SecurityContextHolder.getContext().setAuthentication(authentication);
        return "redirect:/restrito";
    }
}
```

Neste exemplo, a classe `AuthenticationManager` é usada para autenticar o usuário e, se a autenticação for bem-sucedida, o usuário é redirecionado para uma página restrita.

3. Implemente a página de login, como explicado anteriormente.

Com esses passos, você implementou a criptografia de senha e a camada de serviço para o sistema de login no seu aplicativo Spring Boot. Certifique-se de ajustar e aprimorar a segurança e a funcionalidade do seu sistema de acordo com os requisitos específicos do seu aplicativo.

## 19) SESSÃO E LOGIN DO USUÁRIO
A implementação de sessões de usuário e login em um aplicativo Spring Boot é fundamental para fornecer uma experiência de autenticação segura. Vou explicar como você pode implementar isso.

**Passo 1: Configurar o Spring Security**

Antes de criar sessões e implementar o login, você deve configurar o Spring Security para gerenciar a autenticação e autorização do seu aplicativo. Isso pode ser feito criando uma classe de configuração.

```java
@Configuration
@EnableWebSecurity
public class SecurityConfig extends WebSecurityConfigurerAdapter {

    @Autowired
    private UsuarioDetailsService usuarioDetailsService;

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http
            .authorizeRequests()
                .antMatchers("/public/**").permitAll()
                .anyRequest().authenticated()
                .and()
            .formLogin()
                .loginPage("/login")
                .permitAll()
                .and()
            .logout()
                .permitAll();
    }

    @Override
    protected void configure(AuthenticationManagerBuilder auth) throws Exception {
        auth.userDetailsService(usuarioDetailsService).passwordEncoder(passwordEncoder());
    }

    @Bean
    public PasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder();
    }
}
```

Neste exemplo, estamos usando o Spring Security para proteger recursos e configurar a página de login.

**Passo 2: Criar a Entidade de Sessão do Usuário**

Crie uma entidade que represente a sessão do usuário. Esta entidade pode conter informações como o ID do usuário, seu nome e outras informações relevantes para a sessão. Aqui está um exemplo simples:

```java
@Entity
public class UsuarioSessao {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String nome;
    private Long usuarioId;
    
    // Getters e setters
}
```

**Passo 3: Criar um Repositório de Sessão do Usuário**

Crie um repositório para a entidade `UsuarioSessao` para que você possa interagir com o banco de dados e gerenciar as sessões dos usuários.

```java
public interface UsuarioSessaoRepository extends JpaRepository<UsuarioSessao, Long> {
    UsuarioSessao findByUsuarioId(Long usuarioId);
}
```

**Passo 4: Implementar o Serviço de Sessão**

Crie um serviço que gerencie a criação e recuperação de sessões do usuário. Este serviço pode ser usado para criar uma sessão após o login bem-sucedido e recuperar informações da sessão quando necessário.

```java
@Service
public class UsuarioSessaoService {

    @Autowired
    private UsuarioSessaoRepository usuarioSessaoRepository;

    public UsuarioSessao criarSessao(Long usuarioId, String nome) {
        UsuarioSessao sessao = new UsuarioSessao();
        sessao.setUsuarioId(usuarioId);
        sessao.setNome(nome);
        return usuarioSessaoRepository.save(sessao);
    }

    public UsuarioSessao obterSessao(Long usuarioId) {
        return usuarioSessaoRepository.findByUsuarioId(usuarioId);
    }
}
```

**Passo 5: Após o Login Bem-Sucedido, Crie a Sessão do Usuário**

Após o login bem-sucedido, você pode usar o serviço `UsuarioSessaoService` para criar uma sessão para o usuário. Isso geralmente é feito no controlador de login.

```java
@Controller
public class LoginController {

    @Autowired
    private AuthenticationManager authenticationManager;

    @Autowired
    private UsuarioDetailsService usuarioDetailsService;

    @Autowired
    private UsuarioSessaoService usuarioSessaoService;

    @GetMapping("/login")
    public String login() {
        return "login";
    }

    @PostMapping("/login")
    public String realizarLogin(@RequestParam String email, @RequestParam String senha, HttpSession session) {
        UsernamePasswordAuthenticationToken token = new UsernamePasswordAuthenticationToken(email, senha);
        Authentication authentication = authenticationManager.authenticate(token);
        SecurityContextHolder.getContext().setAuthentication(authentication);

        UserDetails userDetails = usuarioDetailsService.loadUserByUsername(email);
        UsuarioSessao sessao = usuarioSessaoService.criarSessao(((Usuario) userDetails).getId(), userDetails.getUsername());

        session.setAttribute("sessaoUsuario", sessao);

        return "redirect:/restrito";
    }
}
```

**Passo 6: Proteger Recursos e Verificar a Sessão do Usuário**

Você pode usar anotações como `@PreAuthorize` para proteger recursos restritos e verificar se a sessão do usuário está ativa. Por exemplo:

```java
@PreAuthorize("isFullyAuthenticated()")
@RequestMapping("/restrito")
public String recursoRestrito() {
    return "restrito";
}
```

Isso garante que apenas usuários autenticados e com sessão ativa tenham acesso a recursos restritos.

**Passo 7: Implementar o Logout**

Você também deve implementar a funcionalidade de logout para encerrar a sessão do usuário. Isso pode ser feito em um controlador dedicado:

```java
@Controller
public class LogoutController {

    @GetMapping("/logout")
    public String logout(HttpSession session) {
        session.invalidate(); // Encerra a sessão do usuário
        return "redirect:/login";
    }
}
```

**Passo 8: Implementar a Página de Sessão Ativa**

Você pode criar uma página onde os usuários possam verificar informações sobre sua sessão ativa, como seu nome e outras informações. Certifique-se de verificar a sessão do usuário e exibir as informações apropriadas.

Com esses passos, você implementou sessões de usuário e login em seu aplicativo Spring Boot. Certifique-se de ajustar e aprimorar a segurança e a funcionalidade de acordo com os requisitos específicos do seu aplicativo.

## 20) DEPLOY DA APLICAÇÃO NO HEROKU - END OF COURSE
Implantar uma aplicação Spring Boot no Heroku é um processo relativamente direto. Vou guiá-lo pelos passos gerais para fazer o deploy de uma aplicação Spring Boot no Heroku no final do curso.

**Passo 1: Certificar-se de que a aplicação está pronta**

Antes de implantar no Heroku, sua aplicação Spring Boot deve estar completamente pronta para produção. Isso inclui a configuração do banco de dados, propriedades de produção, e qualquer outra configuração específica do ambiente de produção.

**Passo 2: Configurar um repositório Git**

Certifique-se de que seu projeto Spring Boot esteja em um repositório Git. Se você ainda não configurou o Git, pode fazer isso com os seguintes comandos:

```bash
git init
git add .
git commit -m "Primeiro commit"
```

**Passo 3: Criar um arquivo `Procfile`**

O Heroku requer um arquivo chamado `Procfile` que informa como iniciar sua aplicação. Crie um arquivo chamado `Procfile` (sem extensão de arquivo) na raiz do seu projeto com o seguinte conteúdo:

```
web: java -jar seu-arquivo-spring-boot.jar
```

Substitua `seu-arquivo-spring-boot.jar` pelo nome do arquivo JAR da sua aplicação Spring Boot.

**Passo 4: Criar um arquivo `system.properties` (opcional)**

Se você precisar definir uma versão específica do Java, crie um arquivo `system.properties` na raiz do seu projeto com o seguinte conteúdo:

```
java.runtime.version=11
```

Isso define a versão do Java que o Heroku usará.

**Passo 5: Criar um arquivo `application.properties` para produção**

Certifique-se de que suas configurações de aplicação no arquivo `application.properties` estejam ajustadas para um ambiente de produção. Isso pode incluir configurações de banco de dados, segurança e outras configurações específicas para produção.

**Passo 6: Criar uma conta no Heroku**

Se você ainda não tem uma conta no Heroku, crie uma em https://signup.heroku.com/.

**Passo 7: Instalar o Heroku CLI**

Para implantar sua aplicação no Heroku, você precisará da Heroku Command Line Interface (CLI). Você pode fazer o download e instalá-lo de acordo com as instruções em https://devcenter.heroku.com/articles/heroku-cli.

**Passo 8: Fazer o login no Heroku**

Após instalar o Heroku CLI, abra o terminal e execute o seguinte comando para fazer o login na sua conta Heroku:

```bash
heroku login
```

Siga as instruções para fazer o login.

**Passo 9: Criar um aplicativo Heroku**

No terminal, navegue até o diretório do seu projeto Spring Boot e execute os seguintes comandos para criar um aplicativo no Heroku:

```bash
heroku create nome-do-seu-aplicativo
```

Substitua `nome-do-seu-aplicativo` pelo nome desejado para o seu aplicativo no Heroku.

**Passo 10: Implantar a aplicação**

Agora, você pode implantar sua aplicação no Heroku com o seguinte comando:

```bash
git push heroku master
```

O Heroku implantará automaticamente a aplicação, configurará as variáveis de ambiente e executará o comando especificado no `Procfile`.

**Passo 11: Acessar a aplicação implantada**

Após a implantação, você pode acessar sua aplicação no navegador com o seguinte comando:

```bash
heroku open
```

A URL da sua aplicação será exibida no terminal.

Agora, sua aplicação Spring Boot está implantada no Heroku e pode ser acessada online. Certifique-se de monitorar os registros e ajustar as configurações conforme necessário para atender às necessidades do seu aplicativo em um ambiente de produção.