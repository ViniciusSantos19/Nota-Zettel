260320242235
Status: #idea #Fleeting 
Tags:  #Programação #web #Spring 
# Paginação e ordenação Spring
## Resumo do trecho sobre paginação e ordenação

Este trecho aborda os recursos de paginação e ordenação oferecidos pelo Spring Data REST.

**Paginação**

Por padrão, as endpoints do Spring Data REST retornam um máximo de 20 itens por página, sendo a primeira página a padrão. É possível ajustar o tamanho da página (`size`) e a página (`page`) através de parâmetros na URL da requisição.

Exemplos:

- Solicitar a primeira página com 5 itens: `localhost:8080/data-api/tacos?size=5`
- Solicitar a segunda página com 5 itens: `localhost:8080/data-api/tacos?size=5&page=1` (atente que a paginação é zero-based)

**Ordenação**

O parâmetro `sort` permite ordenar os resultados da lista por qualquer propriedade da entidade.

Exemplo: Solicitar as 12 últimas criadas tacos ordenadas por data de criação decrescente:

```
localhost:8080/data-api/tacos?sort=createdAt,desc&page=0&size=12
```

Este tipo de ordenação possibilita a criação de endpoints similares ao que você definiu anteriormente em `TacoController` (`/api/tacos?recent`).
*
## References
[[[Habilitando serviços baseados em dados com Spring Data REST]]]
[[Manipulando Requisições DELETE com Spring MVC]]
*
