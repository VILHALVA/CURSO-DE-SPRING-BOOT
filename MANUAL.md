# MANUAL
Para começar com o desenvolvimento de uma aplicação usando **Spring Boot**, você precisará instalar algumas ferramentas essenciais, configurar seu ambiente e criar o primeiro projeto.

## 1. INSTALAÇÕES NECESSÁRIAS:
Antes de começar, instale as seguintes ferramentas no seu computador:

- **JDK (Java Development Kit)**: O Spring Boot requer o JDK 8 ou superior. Você pode baixar o JDK a partir do [site oficial da Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) ou utilizar uma distribuição open-source como o OpenJDK.
  - Verifique se o JDK está instalado corretamente com o comando:
    ```bash
    java -version
    ```

- **Maven** (ou **Gradle**, dependendo da sua escolha): [Maven](https://maven.apache.org/download.cgi) é a ferramenta mais comum para gerenciar dependências em projetos Spring Boot. Ele já vem com suporte nativo ao Spring Boot, mas também é possível usar o Gradle.

  - Verifique a instalação do Maven:
    ```bash
    mvn -version
    ```

- **IDE**: Recomendo o uso do **IntelliJ IDEA** (de preferência a versão Ultimate, que oferece melhor integração com Spring Boot) ou o **Eclipse** (com suporte ao Spring Boot via plugins).

## 2. CRIAR O PRIMEIRO PROJETO:
Para criar o projeto Spring Boot, você pode usar o **Spring Initializr**, que é uma interface web ou plugin integrado na maioria das IDEs para gerar rapidamente a estrutura básica de um projeto.

### USANDO O SPRING INITIALIZR (INTERFACE WEB):
1. Acesse [Spring Initializr](https://start.spring.io/).
2. Selecione as configurações do seu projeto:
   - **Project**: Maven (ou Gradle, se preferir)
   - **Language**: Java
   - **Spring Boot Version**: Selecione a versão mais recente estável (ex: 3.x.x)
   - **Group**: Exemplo: `com.example`
   - **Artifact**: Nome do seu projeto (ex: `meu-primeiro-projeto`)
   - **Name**: Nome da sua aplicação (ex: `meu-primeiro-projeto`)
   - **Packaging**: Jar (ou War se você pretende implantar em um servidor de aplicativos como Tomcat)
   - **Java Version**: Selecione a versão do Java que você instalou (ex: 17)
3. Escolha as **Dependências** necessárias. Você pode começar com:
   - **Spring Web**: Para construir uma API web REST.
   - **Spring Boot DevTools**: Para facilitar o desenvolvimento com live reload.
   - **Lombok**: Para reduzir o boilerplate de código com anotações.
4. Clique em **Generate** para baixar o projeto.

### USANDO O SPRING INITIALIZR VIA IDE:
1. No IntelliJ IDEA ou Eclipse, você pode selecionar a opção "Criar Novo Projeto" e escolher "Spring Initializr".
2. Preencha as mesmas configurações do passo anterior e selecione as dependências necessárias.

## 3. ESTRUTURA DO DIRETÓRIO:
Após gerar o projeto, a estrutura básica de diretórios será algo como:

```
meu-primeiro-projeto
├── mvnw
├── mvnw.cmd
├── pom.xml  (ou build.gradle se estiver usando Gradle)
└── src
    ├── main
    │   ├── java
    │   │   └── com
    │   │       └── example
    │   │           └── meuprimeiroprojeto
    │   │               └── MeuPrimeiroProjetoApplication.java
    │   └── resources
    │       ├── application.properties (ou application.yml)
    │       └── static (pasta para arquivos estáticos, como HTML, CSS)
    └── test
        ├── java
        │   └── com
        │       └── example
        │           └── meuprimeiroprojeto
        │               └── MeuPrimeiroProjetoApplicationTests.java
```

- O arquivo **`pom.xml`** é o arquivo de configuração do Maven. Ele define as dependências do projeto.
- A pasta **`src/main/java`** contém o código-fonte Java da aplicação.
- A pasta **`src/main/resources`** armazena arquivos de configuração e recursos estáticos como HTML, CSS e arquivos de configuração (por exemplo, `application.properties`).
- A pasta **`src/test/java`** é para os testes de unidade.

## 4. EXECUTAR O PROJETO:
Você pode executar o seu projeto de várias maneiras:

### VIA IDE:
1. Navegue até a classe principal do projeto, que será algo como **`MeuPrimeiroProjetoApplication.java`**.
2. Clique com o botão direito na classe e selecione "Run 'MeuPrimeiroProjetoApplication'".

### VIA MAVEN:
1. Abra o terminal na pasta raiz do projeto e execute o comando:
   ```bash
   mvn spring-boot:run
   ```

### VIA JAR:
1. Se você já construiu o JAR (executando `mvn clean package`), poderá rodar o projeto assim:
   ```bash
   java -jar target/meu-primeiro-projeto-0.0.1-SNAPSHOT.jar
   ```

## 5. ACESSAR A APLICAÇÃO:
Após rodar o projeto, o Spring Boot usa, por padrão, a porta **8080**. Você pode abrir o navegador e acessar: [http://localhost:8080](http://localhost:8080)

Se você quiser mudar a porta ou outras configurações, edite o arquivo **`application.properties`** dentro da pasta `src/main/resources`:

```properties
server.port=8081
```

## 6. PRÓXIMOS PASSOS:
Agora que o projeto está rodando, você pode começar a desenvolver seus **endpoints REST**, por exemplo, criando um controlador simples:

```java
@RestController
public class HelloController {
    
    @GetMapping("/hello")
    public String hello() {
        return "Hello, Spring Boot!";
    }
}
```

## CONCLUSÃO:
Esses são os passos básicos para começar com Spring Boot. Depois de configurar e rodar seu primeiro projeto, você pode explorar tópicos mais avançados, como a integração com bancos de dados (usando Spring Data JPA), segurança com Spring Security, testes unitários e muito mais.