240320241804
Status: #idea #Fleeting 
Tags: #Programação #Spring 
# Ambiente e Propriedades de Configuração (Spring Environment and Configuration Properties)
**Resumo:**

- O Spring Environment é uma abstração que centraliza o acesso a propriedades configuráveis da aplicação.
- Ele agrega propriedades de diversas fontes, como variáveis de ambiente, argumentos de linha de comando e arquivos de configuração.
- Propriedades do Spring Environment podem ser acessadas por beans da aplicação.

**Principais Fontes de Propriedades:**

- Propriedades do Sistema JVM
- Variáveis de Ambiente do Sistema Operacional
- Argumentos de Linha de Comando
- Arquivos de Propriedades (ex.: application.properties, application.yml)

**Exemplo: Configurando a porta do servidor**

- Propriedade: `server.port`
- Arquivo application.properties: `server.port=9090`
- Arquivo application.yml:

```
server:
  port: 9090
```
- Linha de comando: `java -jar app.jar --server.port=9090`
- Variável de ambiente: `export SERVER_PORT=9090` (Spring interpreta como `server.port`)

**Vantagens:**

- Flexibilidade na definição de propriedades.
- Separação de concerns (configuração separada da lógica da aplicação).

**Configuração de DataSource:**

- Spring Boot autoconfigura DataSource por padrão (H2 para desenvolvimento).
- Propriedades para configuração manual:
    - `spring.datasource.url` (URL do banco de dados)
    - `spring.datasource.username` (Nome de usuário)
    - `spring.datasource.password` (Senha)
    - `spring.datasource.driver-class-name` (Classe do driver JDBC - opcional)
- Spring Boot usa pool de conexões (HikariCP ou alternativas).
- Propriedades para scripts de inicialização:
    - `spring.datasource.schema` (Lista de scripts para criação de tabelas)
    - `spring.datasource.data` (Lista de scripts com dados iniciais)

**JNDI:**

- Configuração alternativa utilizando JNDI.
- Propriedade: `spring.datasource.jndi-name` (Nome JNDI do DataSource)
- Ao definir `jndi-name`, outras propriedades de conexão são ignoradas.
*
## References
*
