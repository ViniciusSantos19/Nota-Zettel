200420242136
Status: #idea
Tags: #Spring #Java  
# Quinto passo. Configurar beans para assinatura do jwt
Após o último passo de gerar as chaves públicas e privadas agora nós temos que configurar esse bean que pega as chaves e coloca ela na classe JwkSet. Esse é o algoritmo necessário para fazer isso.

```
 @Bean
    public JWKSet jwkSet(AuthProperties authProperties) throws Exception {
        final var jksProperties = authProperties.getJks();
        final String jksPath = jksProperties.getPath();
        final InputStream inputStream = new ClassPathResource(jksPath).getInputStream();

        final KeyStore keyStore = KeyStore.getInstance("JKS");
        keyStore.load(inputStream, jksProperties.getStorepass().toCharArray());

        RSAKey rsaKey = RSAKey.load(keyStore,
                jksProperties.getAlias(),
                jksProperties.getKeypass().toCharArray());

        return new JWKSet(rsaKey);
    }
```

### O próximo
O próximo passo seria dar um set nesse JwkSet, pois um aplicação pode ter mais de uma chave, então temos que deixar explícito  qual será a chave que vamos usar. Esse seria o algoritmo.

```
@Bean
    public JWKSource<SecurityContext> jwkSource(JWKSet jwkSet) {
        return ((jwkSelector, securityContext) -> jwkSelector.select(jwkSet));
    }
```

### Último passo desse tutorial

Como último passo dessa etapa de configuração do nosso server de autenticação precisamos criar esse último bean de encoder que vai usar como base  a chave que foi criada. O algoritmo usado será.

```
 @Bean
    public JwtEncoder jwtEncoder(JWKSource<SecurityContext> jwkSource){
        return new NimbusJwsEncoder(jwkSource);
    }
```

*
## References
[[[Gerando par de chaves assimétricas e JWKS para assinar o Token JWT]]]
[[Segundo passo para criar um servidor de autenticação em java spring]]
*
