090220242022
Status: #idea #Fleeting 
Tags: #Javascript #Programação 
# Explicando como a event queue funciona

```
function testeQueue(tempo) {
  const futuro = Date.now() + tempo
  while (Date.now() < futuro) { }
}

setTimeout(() => console.log('Exec #01'), 3000)
setTimeout(() => console.log('Exec #02'), 300)

testeQueue(5000)
console.log('Fim!')
```

## Explicando um pouco o código
Esse código do curso de programação funcional de grupo cod3rs explica um pouco como a event queue funciona.
1. Função testeQueue(tempo) tem como parametro um tempo que sera usado para determinar o valor da variável futuro. Enquanto o tempo de agora for menor que o valor de futuro. o loop vai rodar. Isso foi feito para atrasar um pouco o código para poder demonstrar como as prioridades funcionam.
2. 2 As linhas de setTimeout() fazem basicamente a mesma coisa. depois que passar o tempo que esta no parâmetro se passar a função que esta no primeiro parâmetro será rodada. Nesse exemplo a primeira função tem o parâmetro de 3 segundos, enquanto a  segunda de apenas 3 milissegundos, então como a prioridade da segunda função é maior que a primeira mesmo ela sendo colocada depois na stack ela termina de ser processada primeiro.
*
## References
[[Stack em Javascript]]
[[Event Queue]]
[[zettels/Como o Javascript funciona|Como o Javascript funciona]]
*
