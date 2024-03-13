090220242100
Status: #idea #Fleeting 
Tags: #Programação #Javascript 
# Explorando o Contexto do "this" em JavaScript
```
function compararComThis(parametro) {
  console.log(this === parametro);
}
const obj = {};
compararComThis = compararComThis.bind(obj);
compararComThis(global);
compararComThis(obj)

let compararComThisArrow = (param) => console.log(this === param);

compararComThisArrow(global);
compararComThisArrow(module.exports);

```
## Explicando o código 
O código apresentado demonstra a diferença entre o uso de funções normais e funções de seta em relação ao contexto do "this" em JavaScript. Começamos com a definição de uma função `compararComThis`, que verifica se o "this" dentro da função é estritamente igual ao parâmetro passado. Em seguida, criamos um objeto vazio chamado `obj`. A função `compararComThis` é então vinculada ao objeto `obj` usando o método `bind`.

As chamadas subsequentes à função `compararComThis`, passando `global` e `obj` como argumentos, demonstram a mudança no contexto do "this" após a vinculação da função com `obj`. Enquanto `this` dentro da função vinculada se refere a `obj`, fora da função, continua referenciando o objeto global.

Em seguida, introduzimos uma função de seta chamada `compararComThisArrow`, que não tem seu próprio "this" e herda o "this" do escopo em que foi definida. Chamadas subsequentes a esta função, passando `global` e `module.exports` como argumentos, sempre imprimirão `true`, independentemente do argumento passado, pois as funções de seta herdam o "this" do escopo em que foram definidas.

## Conclusão
O código fornece uma compreensão prática do contexto do "this" em JavaScript, destacando as diferenças entre funções normais e funções de seta. Isso é crucial para entender o comportamento das funções em diferentes situações e ajuda a evitar erros comuns relacionados ao "this" em JavaScript.
*
## References
[[[zettels/Como o Javascript funciona|Como o Javascript funciona]]]
[[[]]]
*
