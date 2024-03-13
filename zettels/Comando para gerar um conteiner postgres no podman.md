120220242119
Status: #idea #Fleeting 
Tags: #Conteiners #Infraestrutura
# Comando para gerar um conteiner postgres no podman
```
podman run --name postgres -e POSTGRES_USER=username -e POSTGRES_PASSWORD=password -p 5432:5432 -v /var/lib/data -d postgres

```
Esse comando roda um conteiner com o node postgres com senha e usuário na porta 5432, e salva no volume que esta ai no final

*
## References
*
