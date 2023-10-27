# UTILIZANDO BIBLIOTECA WEBJARS NO PROJETO
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