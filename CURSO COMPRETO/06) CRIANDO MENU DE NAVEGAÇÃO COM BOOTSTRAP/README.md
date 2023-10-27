# CRIANDO MENU DE NAVEGAÇÃO COM BOOTSTRAP
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