# CURSO DE SPRING BOOT
👨‍⚖️SPRING BOOT É UM FRAMEWORK DE DESENVOLVIMENTO DE APLICATIVOS JAVA QUE SIMPLIFICA A CONFIGURAÇÃO E O DESENVOLVIMENTO DE APLICATIVOS BASEADOS EM SPRING. ELE FORNECE UMA ESTRUTURA PRONTA PARA USO, QUE INCLUI CONFIGURAÇÃO AUTOMÁTICA, GERENCIAMENTO DE DEPENDÊNCIAS E UM SERVIDOR EMBUTIDO, FACILITANDO A CRIAÇÃO DE APLICATIVOS JAVA DE FORMA RÁPIDA E EFICIENTE.

[![GitHub Repo stars](https://img.shields.io/badge/VILHALVA-GITHUB-03A9F4?logo=github)](https://github.com/VILHALVA) 
[![GitHub Repo stars](https://img.shields.io/badge/VEJA-DOCUMENTAÇÃO-03A9F4?logo=google)](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/)
[![GitHub Repo stars](https://img.shields.io/badge/LINGUAGEM%20DE-PROGRAMAÇÃO-03A9F4?logo=github)](https://github.com/VILHALVA/CURSO-DE-JAVA) 
[![GitHub Repo stars](https://img.shields.io/badge/-PLAYLIST%20DO%20YOUTUBE-blueviolet)](https://youtube.com/playlist?list=PL0j7juv7l4HgSY7gNDzNQjgwEA5s4hzjx&si=P6w-CHYBz_VrEaQI)

# CONCEITO:
O Spring Boot é uma estrutura que simplifica o desenvolvimento de aplicativos Java, facilitando a criação de aplicativos web, microserviços e aplicativos empresariais. Ele fornece muitas funcionalidades e abstrai grande parte da configuração, tornando o desenvolvimento mais rápido e fácil.

Vamos começar com um conceito fundamental do Spring Boot e, em seguida, você pode fazer perguntas mais específicas ou solicitar exemplos de código quando necessário.

1. **Inversão de Controle (IoC) e Injeção de Dependência:**

   O Spring Boot é construído com base no princípio da Inversão de Controle (IoC) e Injeção de Dependência. Isso significa que o controle do ciclo de vida e a gestão de componentes são transferidos para o framework. O Spring gerencia os objetos e suas dependências, em vez de você fazer isso manualmente.

   **Exemplo:**

   Suponha que você tenha uma classe `ClienteService` que depende de uma implementação da interface `ClienteRepository`. Com o Spring Boot, você pode definir essas classes como componentes gerenciados e o Spring injetará automaticamente a instância correta do `ClienteRepository` no `ClienteService`.

   ```java
   @Service
   public class ClienteService {
       private final ClienteRepository clienteRepository;

       @Autowired
       public ClienteService(ClienteRepository clienteRepository) {
           this.clienteRepository = clienteRepository;
       }

       // Outros métodos da classe
   }
   ```

   Dessa forma, o Spring cuida da resolução de dependências, tornando seu código mais modular e fácil de manter.

# CARACTERISTICAS:
## Características Positivas:
1. **Facilita o Desenvolvimento Rápido:** O Spring Boot abstrai grande parte da configuração, o que permite que os desenvolvedores se concentrem mais na lógica de negócios em vez de gastar tempo configurando detalhes técnicos.

2. **Convenção sobre Configuração:** O Spring Boot segue convenções que facilitam o desenvolvimento, como a estrutura de diretórios padrão para organizar o código-fonte.

3. **Autoconfiguração:** O Spring Boot oferece recursos de autoconfiguração inteligente, o que significa que ele tenta configurar automaticamente os componentes com base nas bibliotecas e dependências encontradas no projeto.

4. **Gestão de Dependência:** O Spring Boot integra o Spring Framework com o Apache Maven ou o Gradle para gerenciar as dependências, tornando mais fácil adicionar bibliotecas e atualizá-las.

5. **Embutibilidade de Servidores:** O Spring Boot oferece servidores embutidos, como Tomcat, Jetty e Undertow, o que significa que você pode criar aplicativos web executáveis com um servidor incorporado.

6. **Suporte a Microserviços:** O Spring Boot é uma escolha popular para o desenvolvimento de microserviços devido à facilidade de criação, implantação e escalabilidade.

7. **Segurança:** O Spring Boot oferece recursos integrados para configuração de segurança, facilitando a implementação de autenticação e autorização em aplicativos.

## Características Negativas:
1. **Complexidade:** Embora o Spring Boot simplifique muito o desenvolvimento, ele ainda pode ser complexo, especialmente para iniciantes. A sobrecarga de recursos e anotações pode ser confusa.

2. **Tamanho do Pacote:** Os aplicativos Spring Boot podem ter um tamanho de pacote significativo devido às bibliotecas e dependências incorporadas. Isso pode afetar o tempo de inicialização e o uso de recursos.

3. **Possível Desempenho Menor:** Devido à conveniência e à abstração fornecida pelo Spring Boot, pode haver um pequeno custo de desempenho em comparação com aplicativos Java tradicionais.

4. **Curva de Aprendizado:** Embora o Spring Boot seja mais fácil de usar do que a configuração manual, ainda existe uma curva de aprendizado, especialmente para aproveitar ao máximo seus recursos avançados.

