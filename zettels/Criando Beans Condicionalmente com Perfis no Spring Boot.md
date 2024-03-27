250320241140
Status: #idea #Fleeting 
Tags: #Spring #Programação #web 
# Criando Beans Condicionalmente com Perfis no Spring Boot
Às vezes, é útil fornecer um conjunto único de beans para diferentes perfis. Normalmente, qualquer bean declarado em uma classe de configuração Java é criado, independentemente do perfil ativo. Mas suponha que você precise que alguns beans sejam criados apenas se um determinado perfil estiver ativo. Nesse caso, a anotação @Profile pode designar beans como sendo aplicáveis apenas a um determinado perfil.

Por exemplo, digamos que você tenha um bean `CommandLineRunner` declarado em `TacoCloudApplication` usado para carregar o banco de dados embutido com dados de ingredientes quando o aplicativo é iniciado. Isso é ótimo para desenvolvimento, mas seria desnecessário (e indesejável) em um aplicativo de produção. Para evitar que os dados do ingrediente sejam carregados toda vez que o aplicativo é iniciado em uma implantação de produção, você pode anotar o método `CommandLineRunner` com `@Profile` assim:

Java

```
@Bean
@Profile("dev")
public CommandLineRunner dataLoader(IngredientRepository repo, UserRepository userRepo, PasswordEncoder encoder) {
  // ...
}
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

Ou suponha que você precise do `CommandLineRunner` criado se o perfil `dev` ou `qa` estiver ativo. Nesse caso, você pode listar os perfis para os quais o bean deve ser criado:

Java

```
@Bean
@Profile({"dev", "qa"})
public CommandLineRunner dataLoader(IngredientRepository repo, UserRepository userRepo, PasswordEncoder encoder) {
  // ...
}
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

Agora, os dados do ingrediente serão carregados somente se os perfis `dev` ou `qa` estiverem ativos. Isso significa que você precisaria ativar o perfil `dev` ao executar o aplicativo no ambiente de desenvolvimento. Seria ainda mais conveniente se esse bean `CommandLineRunner` fosse sempre criado, a menos que o perfil `prod` esteja ativo. Nesse caso, você pode aplicar `@Profile` assim:

Java

```
@Bean
@Profile("!prod")
public CommandLineRunner dataLoader(IngredientRepository repo, UserRepository userRepo, PasswordEncoder encoder) {
  // ...
}
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

Aqui, o ponto de exclamação (!) nega o nome do perfil. Efetivamente, ele afirma que o bean `CommandLineRunner` será criado se o perfil `prod` não estiver ativo.

Também é possível usar `@Profile` em uma classe inteira anotada com `@Configuration`. Por exemplo, suponha que você extraísse o bean `CommandLineRunner` em uma classe de configuração separada chamada `DevelopmentConfig`. Então você poderia anotar `DevelopmentConfig` com `@Profile` da seguinte forma:

Java

```
@Profile({"!prod", "!qa"})
@Configuration
public class DevelopmentConfig {
  @Bean
  public CommandLineRunner dataLoader(IngredientRepository repo, UserRepository userRepo, PasswordEncoder encoder) {
    // ...
  }
}
```
*
## References
[[Ativando Perfis no Spring Boot]]
*
