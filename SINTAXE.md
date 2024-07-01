# SINTAXE
Passo 1: Acesse o site do [Spring Initializr](https://start.spring.io/).

Passo 2: Escolha as configurações do projeto:

   - Project: Selecione "Maven Project" ou "Gradle Project", dependendo de sua preferência de gerenciamento de dependências.
   - Language: Selecione "Java".
   - Spring Boot: Escolha a versão do Spring Boot que deseja utilizar.
   - Group e Artifact: Esses campos definem o identificador do seu projeto. O Group é usado para organizar projetos relacionados e o Artifact é o nome do projeto em si.
   - Dependencies: Selecione as dependências que deseja adicionar ao projeto. Por exemplo, selecione "Spring Web" para criar um aplicativo da web básico.

Passo 3: Clique no botão "Generate" para baixar o arquivo ZIP do projeto.

Passo 4: Extraia o arquivo ZIP em um diretório de sua escolha.

Passo 5: Importe o projeto em sua IDE preferida. Por exemplo, se você estiver usando o Eclipse, siga estas etapas:

   - No Eclipse, vá para "File" > "Import".
   - Selecione "Existing Maven Projects" e clique em "Next".
   - Navegue até o diretório onde você extraiu o projeto e clique em "Finish".

Passo 6: Aguarde a importação do projeto e a resolução das dependências.

Passo 7: Após a importação, você verá a estrutura básica do projeto, incluindo arquivos como `pom.xml` (para projetos Maven), `build.gradle` (para projetos Gradle) e a estrutura de pacotes do Java.

Passo 8: Você pode começar a adicionar código ao seu projeto. Por exemplo, você pode criar controladores para manipular solicitações HTTP, serviços para a lógica de negócios e modelos para representar dados.

Aqui está um exemplo simples de um controlador em Spring Boot:

```java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloController {

    @GetMapping("/hello")
    public String hello() {
        return "Hello, world!";
    }
}
```

Este controlador define um endpoint `/hello` que retorna a string "Hello, world!" quando acessado via HTTP GET.

Passo 9: Execute o aplicativo Spring Boot. Você pode fazer isso clicando com o botão direito do mouse no arquivo principal do aplicativo (normalmente chamado `Application` ou `Main`) e selecionando "Run As" > "Java Application" na maioria das IDEs. Ou, se preferir, você pode executar o projeto usando o Maven ou o Gradle na linha de comando.

Parabéns! Você criou com sucesso um projeto básico em Spring Boot. Este é apenas o começo; você pode expandir e personalizar o projeto conforme necessário para atender aos requisitos do seu aplicativo.