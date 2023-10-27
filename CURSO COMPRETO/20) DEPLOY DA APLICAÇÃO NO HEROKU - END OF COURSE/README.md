# DEPLOY DA APLICAÇÃO NO HEROKU - END OF COURSE
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