100220241842
Status: #idea #Fleeting 
Tags: #Programação #Javascript #Funcional 
# Como passar uma função como um parâmetro para outra em Js
Para se passar uma função como parâmetro para outra em Javascript é simples, porém você tem que tomar cuidado com o tipo do objeto que esta sendo passado para a função. Antes de passar você tem que checar o typeof do objeto, se ele for to tipo 'function'. Caso o o objeto seja do tipo function será possível executar essa função.
```

function bomDia() {
  console.log('Boa dia')
}

function boaTarde() {
  console.log('Boa tarde')
}

function testeFuncao(fn) {
  if (typeof fn == 'function') {
    fn()
  }
}


testeFuncao(bomDia)
testeFuncao(boaTarde)


```
O resultado desse código será o output das funções
*
## References
[[zettels/Como o JavaScript funciona|Como o JavaScript funciona]]
[[Programação funcional]]
*
