# SESSÃO E LOGIN DO USUÁRIO
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