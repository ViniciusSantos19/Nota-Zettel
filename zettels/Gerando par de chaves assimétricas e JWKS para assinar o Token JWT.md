200420242113
Status: #idea
Tags: 
# Gerando par de chaves assimétricas e JWKS para assinar o Token JWT
Terceiro passo do nosso projeto servidor de autenticação será gerar chaves assimétricas para nosso projeto. O primeiro passo para gerar essas chaves seria usando o comando:

```keytool -genkeypair -alias nome_da_chave -keyalg RSA -keypass senha -keystore nome_do_cofre -storepass senha -validity 365
```
### Depois

Depois de gerar essa chave você deve move-la para o diretório de resources do seu projeto java spring, assim, essa keypair também vai estar no .jar quando você fizer um build no projeto.

O Desenvolvedor também tem que colocar essa chave no seu application.yml. Assim seria um exemplo.

```
aw:
  auth:
    provider-uri: "http://localhost:8082"
    jks:
      keypass: 123456
      storepass: 123456
      alias: awblog
      path: keystore/awblog.jks
```
Esse path esta correto para o arquivo.jks pois quando o java faz o build o diretório resources vira o root.
*
## References
[[Primeiro passo para implementar o servidor de autenticação em spring com oauth2]]
[[Segundo passo para criar um servidor de autenticação em java spring]]
*
