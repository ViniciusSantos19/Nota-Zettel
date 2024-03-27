250320241137
Status: #idea #Fleeting 
Tags: #Programação #web #Spring 
# Ativando Perfis no Spring Boot
**Contexto**: Em aplicações Spring Boot, os perfis são utilizados para configurar diferentes conjuntos de propriedades e beans conforme o ambiente de execução, como desenvolvimento, teste ou produção. É importante entender como ativar esses perfis para garantir que as configurações corretas sejam aplicadas em cada ambiente.

**Ativação de Perfis**:

1. **Definição no arquivo `application.yml` ou `application.properties`**:
    
    - É possível especificar os perfis ativos diretamente no arquivo de configuração, mas isso geralmente não é recomendado.
    - Se feito dessa forma, o perfil especificado se torna o perfil padrão, substituindo os benefícios de usar perfis para separar as propriedades específicas de produção das propriedades de desenvolvimento.
    - Exemplo no arquivo `application.yml`:
    ```
    spring:
  profiles:
    active:
      - prod
    ```
    **Utilização de Variáveis de Ambiente**:

- Recomenda-se definir os perfis ativos utilizando variáveis de ambiente, especialmente em ambientes de produção.
- Exemplo de definição da variável de ambiente `SPRING_PROFILES_ACTIVE`:
    
    bash
    

- - `% export SPRING_PROFILES_ACTIVE=prod`
        
    - Isso garante que o perfil especificado seja ativado sem comprometer a modularidade das configurações.
- **Passagem de Argumento na Linha de Comando**:
    
    - Ao executar o aplicativo como um arquivo JAR, é possível definir o perfil ativo utilizando um argumento na linha de comando.
    - Exemplo de ativação do perfil `prod`:
        
        bash
        
- - `% java -jar taco-cloud.jar --spring.profiles.active=prod`
        
- **Múltiplos Perfis**:
    
    - O nome da propriedade para ativação de perfis é `spring.profiles.active`, permitindo a ativação de mais de um perfil simultaneamente.
    - Exemplo de ativação de múltiplos perfis utilizando variável de ambiente:
        
        bash
        

1. - `% export SPRING_PROFILES_ACTIVE=prod,audit,ha`
        

**Conclusão**: Ativar os perfis corretos é fundamental para garantir que as configurações específicas de cada ambiente sejam aplicadas em uma aplicação Spring Boot. Utilizar variáveis de ambiente ou argumentos na linha de comando oferece flexibilidade e facilita o gerenciamento dos perfis, garantindo a modularidade e a adaptabilidade da aplicação em diferentes ambientes de execução.
*
## References
[[Definindo Propriedades Específicas de Perfil no Spring Boot]
[[Configurando com Perfis no Spring Boot]]
*
