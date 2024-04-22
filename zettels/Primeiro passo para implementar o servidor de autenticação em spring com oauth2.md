
200420242016
Status: #idea
Tags: #Fleeting #Programação #java #Spring #security 
# Primeiro passo para implementar o servidor de autenticação em spring com oauth2

O primeiro passo para implementar um servidor de segurança com o spring seria implementar uma classe de configuração para o servidor. Nessa classe o desenvolvedir precisa ativar o spring security e colocar uma anotação de configuration para que o spring boot entenda para que serve essa classe.

O desenvolvedor tem que implementar o método authFilterChain, que vai retornar um secutiryChain do spring secutiry. Esse método vai servir para configurar o spring secutiry e o oauth2.

Exemplo de código:

```
@Bean
    @Order(Ordered.HIGHEST_PRECEDENCE)
    public SecurityFilterChain defaultFilterChain(HttpSecurity http) throws Exception {
        OAuth2AuthorizationServerConfiguration.applyDefaultSecurity(http);
        return http.formLogin(Customizer.withDefaults()).build();
    }

    @Bean
    public SecurityFilterChain authFilterChain(HttpSecurity http) throws Exception {
        http.authorizeRequests().anyRequest().authenticated();
        return http.formLogin(Customizer.withDefaults()).build();
    }
```


### Final
Esses seriam alguns exemplos para configura o oauth2

*
## References
[[Como iniciar um servidor de autenticação em spring boot]]
*
