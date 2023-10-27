# LOGIN DO USUÁRIO
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