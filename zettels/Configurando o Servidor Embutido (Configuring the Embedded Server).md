240320241812
Status: #idea #Fleeting 
Tags: #Spring #Programação #web 
# Configurando o Servidor Embutido (Configuring the Embedded Server)
**Porta aleatória com server.port=0:**

- Definir `server.port` como `0` resulta em uma porta aleatória disponível.
- Ideal para testes de integração automatizados para evitar conflitos de porta.

**Habilitando HTTPS:**

1. Criar um keystore usando `keytool`:
```
$ keytool -keystore mykeys.jks -genkey -alias tomcat -keyalg RSA
```
Definir propriedades no arquivo `application.properties` ou `application.yml`:
```
server:
  port: 8443  # Porta comum para HTTPS no desenvolvimento
  ssl:
    key-store: file:///path/to/mykeys.jks  # Caminho para o keystore
    key-store-password: letmein  # Senha usada durante a criação do keystore
    key-password: letmein
```
- `server.ssl.key-store`: caminho do arquivo keystore (ou URL classpath se dentro do JAR)
- `server.ssl.key-store-password` e `server.ssl.key-password`: senha usada na criação do keystore

**Observação:**

- Aviso do navegador sobre identidade do servidor durante o desenvolvimento em localhost pode ser ignorado.
*
## References
[[Ambiente e Propriedades de Configuração (Spring Environment and Configuration Properties)]]
*
