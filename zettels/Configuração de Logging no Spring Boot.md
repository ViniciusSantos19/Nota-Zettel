240320241833
Status: #idea
Tags: 
# Configuração de Logging no Spring Boot
O Spring Boot configura o logging por padrão utilizando o Logback para gravar na console em nível INFO.

### Visualizando Logs

Aqui está um exemplo do formato padrão de log:
```
2021-07-29 17:24:24.187 INFO 52240 --- [nio-8080-exec-1]
➥ com.example.demo.Hello
Here's a log entry.
2021-07-29 17:24:24.187 INFO 52240 --- [nio-8080-exec-1]
➥ com.example.demo.Hello
Here's another log entry.
2021-07-29 17:24:24.187 INFO 52240 --- [nio-8080-exec-1]
➥ com.example.demo.Hello
And here's one more.
```
### Configuração Personalizada

Para um controle completo, crie um arquivo `logback.xml` na raiz do classpath (em `src/main/resources`).

Exemplo de um arquivo `logback.xml` simples:
```
<configuration>
  <appender name="STDOUT" class="ch.qos.logback.core.ConsoleAppender">
    <encoder>
      <pattern>%d{HH:mm:ss.SSS} [%thread] %-5level %logger{36} - %msg%n</pattern>
    </encoder>
  </appender>
  <logger name="root" level="INFO"/>
  <root level="INFO">
    <appender-ref ref="STDOUT" />
  </root>
</configuration>
```
Esse arquivo permite ajustar o formato e comportamento do log.

### Propriedades de Configuração

As propriedades com prefixo `logging.level.` definem o nível de log para um registrador específico. Por exemplo:

YAML

```
logging:
  level:
    root: WARN
    org.springframework.security: DEBUG
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

- `root: WARN`: define o nível de log geral para `WARN`.
- `org.springframework.security: DEBUG`: define o nível de log para logs de segurança do Spring como `DEBUG`.

Para gravar logs em um arquivo, use as propriedades `logging.file.path` e `logging.file.name`:

YAML

```
logging:
  file:
    path: /var/logs/
    name: TacoCloud.log
  level:
    root: WARN
    org.springframework.security: DEBUG
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

Isso grava os logs em `/var/logs/TacoCloud.log` com rotação automática ao atingir 10 MB.
*
## References
[[Configurando o Servidor Embutido (Configuring the Embedded Server)]]
[[Ambiente e Propriedades de Configuração (Spring Environment and Configuration Properties)]]
*
