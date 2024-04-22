200420242253
Status: #idea
Tags: #Spring #security #Java  
# Sexto passo. Customizando jwt no spring
Para que possamos consumizar nossa jwt para que ela tenha mais dados do usuário caso a autenticação seja por User precisamos adicionar esse bean:

```
@Bean
    public OAuth2TokenCustomizer<JwtEncodingContext> jwtEncodingContextOAuth2TokenCustomizer(UserRepository userRepository){
        return (context -> {
            Authentication authentication = context.getPrincipal();
            if (authentication.getPrincipal() instanceof User) {
                final User user = (User) authentication.getPrincipal();

                final UserEntity userEntity = userRepository.findByEmail(user.getUsername()).orElseThrow();

                Set<String> authorities = new HashSet<>();
                for (GrantedAuthority authority : user.getAuthorities()) {
                    authorities.add(authority.toString());
                }
                context.getClaims().claim("user_id", userEntity.getId().toString());
                context.getClaims().claim("user_fullname", userEntity.getName());
                context.getClaims().claim("authorities", authorities);
            }

        });
    }
```
*
## References
[[Quinto passo. Configurar beans para assinatura do jwt]]
*
