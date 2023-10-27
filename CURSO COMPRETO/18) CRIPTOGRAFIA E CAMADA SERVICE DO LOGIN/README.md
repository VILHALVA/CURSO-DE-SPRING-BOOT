# CRIPTOGRAFIA E CAMADA SERVICE DO LOGIN
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