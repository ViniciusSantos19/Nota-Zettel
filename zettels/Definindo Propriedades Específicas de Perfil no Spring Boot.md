250320241130
Status: #idea #Fleeting 
Tags: #Spring #Programação #web
# Definindo Propriedades Específicas de Perfil no Spring Boot
**ontexto**: Em aplicações Spring Boot, é comum a necessidade de definir configurações específicas para diferentes perfis de execução, como desenvolvimento, teste e produção. Essas configurações podem incluir detalhes de conexão com banco de dados, níveis de log e outros parâmetros que variam de acordo com o ambiente.

**Objetivo**: Compreender e utilizar as diferentes maneiras de definir propriedades específicas de perfil no Spring Boot, permitindo uma configuração flexível e adaptável para diferentes ambientes de execução.

**Formas de Definição de Propriedades Específicas de Perfil**:

1. **Arquivos Separados para Cada Perfil**:
    
    - Crie um arquivo YAML ou properties separado contendo apenas as propriedades específicas para o perfil de produção.
    - Siga a convenção de nomenclatura: `application-{nome do perfil}.yml` ou `application-{nome do perfil}.properties`.
    - Por exemplo, para o perfil de produção (`prod`), pode-se criar o arquivo `application-prod.yml` com as configurações apropriadas, como:
```
spring:
  datasource:
    url: jdbc:mysql://localhost/tacocloud
    username: tacouser
    password: tacopassword
logging:
  level:
    tacos: WARN
```
**Inclusão de Propriedades no Mesmo Arquivo YAML** (apenas para YAML):

- Coloque as propriedades específicas do perfil junto com as propriedades não relacionadas ao perfil no mesmo arquivo `application.yml`.
- Separe as seções de propriedades de perfil e não perfil com três hifens (`---`) e especifique o perfil utilizando `spring.profiles`.
- Por exemplo, o arquivo `application.yml` pode ser estruturado da seguinte forma:
```
logging:
  level:
    tacos: DEBUG
---
spring:
  profiles: prod
  datasource:
    url: jdbc:mysql://localhost/tacocloud
    username: tacouser
    password: tacopassword
  logging:
    level:
      tacos: WARN

```
**Funcionamento**:

- As propriedades definidas fora de qualquer seção específica de perfil são aplicáveis a todos os perfis ou servem como valores padrão.
- As propriedades definidas dentro de uma seção específica de perfil substituem as propriedades correspondentes definidas fora da seção, quando o perfil correspondente está ativo.

**Conclusão**: A definição de propriedades específicas de perfil no Spring Boot oferece flexibilidade e modularidade na configuração de aplicações para diferentes ambientes de execução. Ao escolher a abordagem adequada, os desenvolvedores podem organizar e gerenciar eficientemente as configurações de acordo com as necessidades de cada ambiente.



*
## References
[[Configurando com Perfis no Spring Boot]]
*
