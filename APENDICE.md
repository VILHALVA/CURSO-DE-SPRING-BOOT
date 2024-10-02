# APÊNDICE
## INSTALAÇÕES:
### 1. INSTALAR O JAVA DEVELOPMENT KIT (JDK):
   - Baixe e instale o JDK mais recente da Oracle ou OpenJDK:
     - [Oracle JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
     - [OpenJDK](https://adoptopenjdk.net/)
   - Certifique-se de selecionar a versão adequada para o seu sistema operacional.

### 2. CONFIGURAR A VARIÁVEL DE AMBIENTE JAVA_HOME:
   - No Windows:
     - [Configurando a variável de ambiente JAVA_HOME no Windows](https://mkyong.com/java/how-to-set-java_home-on-windows-10/)
   - No Linux/Mac:
     - [Configurando a variável de ambiente JAVA_HOME no Linux](https://linuxize.com/post/how-to-set-and-list-environment-variables-in-linux/)

### 3. INSTALAR UMA IDE (AMBIENTE DE DESENVOLVIMENTO INTEGRADO):
   - IntelliJ IDEA:
     - [Download do IntelliJ IDEA](https://www.jetbrains.com/idea/download/)
   - Eclipse:
     - [Download do Eclipse](https://www.eclipse.org/downloads/)
   - Spring Tool Suite (STS):
     - [Download do Spring Tool Suite](https://spring.io/tools)

### 4. CRIAR UM PROJETO SPRING BOOT:
   - Documentação do Spring Boot:
     - [Documentação oficial do Spring Boot](https://docs.spring.io/spring-boot/docs/current/reference/html/index.html)
   - No IntelliJ IDEA:
     - [Guia para criar um projeto Spring Boot no IntelliJ IDEA](https://www.jetbrains.com/help/idea/spring-boot.html#start)
   - No Eclipse:
     - [Guia para criar um projeto Spring Boot no Eclipse](https://www.baeldung.com/spring-boot-eclipse)

### 5. COMECE A CODIFICAR!
   - Documentação do Spring Framework:
     - [Documentação oficial do Spring Framework](https://docs.spring.io/spring-framework/docs/current/reference/html/index.html)
   - Aproveite os recursos disponíveis na IDE escolhida e explore a vasta documentação e tutoriais online sobre Spring Boot.

## CONFIGURANDO O ECLIPSE:
### 1. **INSTALANDO O PLUGIN PARA DESENVOLVIMENTO HTML**:
   - Abra o Eclipse e vá para o menu "Help" (Ajuda).
   - Selecione "Eclipse Marketplace..." (Mercado Eclipse).
   - Na barra de pesquisa, digite "Web Tools Platform" (WTP) e pressione Enter.
   - Você verá o "Eclipse Web Developer Tools" ou "Eclipse Web Tools Platform", clique em "Install" (Instalar) e siga as instruções para concluir a instalação.
   - Reinicie o Eclipse após a conclusão da instalação.

### 2. **SELECIONANDO O TIPO DE IMPORTAÇÃO DE PROJETO**:
   - Para criar um novo projeto, vá para o menu "File" (Arquivo) -> "New" (Novo) -> "Other..." (Outro).
   - Na janela "Select a wizard" (Selecionar um assistente), expanda a categoria "Web" e selecione "Dynamic Web Project" (Projeto Web Dinâmico) ou "Spring Boot" se estiver trabalhando com Spring Boot.
   - Clique em "Next" (Avançar) e siga as instruções do assistente para configurar seu projeto.

### 3. CRIANDO UM MAVEN BUILD:
   - No Eclipse, abra o projeto Spring Boot no qual você está trabalhando.
   - Certifique-se de que o arquivo `pom.xml` do seu projeto esteja aberto no editor.
   - Clique com o botão direito do mouse no arquivo `pom.xml`.
   - No menu de contexto, vá para "Run As" (Executar Como) -> "Maven build..." (Construção Maven...).

### 4. CONFIGURANDO O MAVEN BUILD:
   - Na janela de configuração da construção do Maven, você verá o campo "Goals" (Metas). Aqui é onde você especifica as metas Maven que deseja executar.
   - No campo "Goals", insira `spring-boot:run`.
   - Certifique-se de que o diretório de trabalho esteja configurado corretamente. Por padrão, ele deve apontar para o diretório raiz do seu projeto.

### 5. EXECUTANDO O MAVEN BUILD:
   - Depois de configurar as metas Maven e o diretório de trabalho, clique em "Run" (Executar).
   - O Maven Build será executado e iniciará seu aplicativo Spring Boot incorporando o servidor web embutido.

### 6. CRIANDO UM ARQUIVO DE CONFIGURAÇÃO (OPCIONAL):
   - Se o seu aplicativo Spring Boot requer um arquivo de configuração específico (por exemplo, `application.properties` ou `application.yml`), você pode criá-lo manualmente no diretório `src/main/resources`.
   - No Eclipse, clique com o botão direito do mouse na pasta `src/main/resources`.
   - Vá para "New" (Novo) -> "File" (Arquivo) e insira o nome do arquivo de configuração desejado.
   - Adicione as configurações necessárias ao arquivo de configuração.

### 7. **SUBINDO O SERVIDOR**:
   - Depois de configurar seu projeto, você pode subir um servidor web para testar seu aplicativo web.
   - No Eclipse, na visualização "Project Explorer" (Explorador de Projetos), clique com o botão direito do mouse no seu projeto.
   - Vá para "Run As" (Executar Como) -> "Run on Server" (Executar no Servidor).
   - Selecione o servidor que você configurou (por exemplo, Apache Tomcat) e clique em "Next" (Avançar).
   - Selecione o projeto que você deseja implantar e clique em "Finish" (Concluir).
   - O Eclipse iniciará o servidor e implantará seu projeto nele. Você poderá acessar seu aplicativo web em um navegador visitando o endereço do servidor local (geralmente http://localhost:8080).
 
