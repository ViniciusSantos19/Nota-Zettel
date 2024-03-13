100220241959
Status: #idea #Fleeting 
Tags: #Programação #Javascript #Funcional 
# Arrow Functions em Js
Arrow Functions são uma sintaxe concisa e poderosa introduzida no ECMAScript 6 (também conhecido como ES2015) para definir funções em JavaScript. Elas oferecem uma forma mais compacta e legível de escrever funções, especialmente para funções de callback e expressões de função.

## Detalhes

#### Sintaxe concisa
1. Arrow Functions fornecem uma sintaxe mais curta e direta em comparação com as funções tradicionais.

	```
	// Função tradicional 
	function soma(a, b) { return a + b; } 
	// Arrow Function
	 let soma = (a, b) => a + b;

	```

#### This léxico
Arrow Functions têm um comportamento de `this` léxico, o que significa que o valor de `this` é herdado do contexto em que a função é definida, não onde é executada.

#### Não há "arguments"
Arrow Functions não têm seu próprio objeto `arguments`. Em vez disso, elas herdam o objeto `arguments` do escopo pai.

#### Não há "new.target"
Arrow Functions também não têm a propriedade `new.target`.

#### Melhor para funções callback
Arrow Functions são particularmente úteis para funções de callback em métodos como `map()`, `filter()`, `reduce()`, etc.

#### Exemplo de uso
```
let numeros = [1, 2, 3, 4, 5];
let quadrados = numeros.map(numero => numero * numero);
```
- **Limitações:**
    
    - Arrow Functions não são adequadas para todas as situações, especialmente quando você precisa do `this` dinâmico ou quando você precisa criar métodos de objeto.
- **Compatibilidade:**
    
    - Arrow Functions são amplamente suportadas em navegadores modernos, mas podem não ser compatíveis com versões mais antigas do JavaScript.
- **Conclusão:**
    
    - As Arrow Functions são uma adição bem-vinda ao JavaScript, oferecendo uma sintaxe mais concisa e elegante para definir funções, especialmente em situações de callback e expressões de função.
*
## References
[[Como retornar uma função a partir de uma outra função em Javascript]]
[[Explorando o Contexto do "this" em JavaScript]]
[[Declaração de função vs Expressão de Função]]
[[zettels/Como o Javascript funciona|Como o Javascript funciona]]
*
