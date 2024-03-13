110220242142
Status: #idea #Fleeting 
Tags: #Programação #Javascript #Funcional 
# Filter em Javascipt
O método `filter()` é uma função de array em JavaScript que cria um novo array contendo todos os elementos de um array original que passam por um teste especificado por uma função de callback. Ele é útil para filtrar elementos de um array com base em determinados critérios.

### Detalhes
- O método `filter()` itera sobre cada elemento do array original e chama uma função de callback fornecida como argumento.
    - A função de callback determina se um elemento atende a um determinado critério. Se o retorno da função de callback for `true`, o elemento é incluído no novo array; se for `false`, o elemento é ignorado.
- **Sintaxe:**
    
    - A sintaxe básica do método `filter()` é a seguinte:
    ```
    const newArray = arrayOriginal.filter(function(elemento) {
    // Retorna true se o elemento deve ser incluído no novo array
});

    ```
- **Callback:**
    
    - A função de callback passada para `filter()` pode receber até três argumentos: `elemento`, `índice` e `array`.
        - `elemento`: O elemento atual sendo processado no array.
        - `índice`: O índice do elemento atual sendo processado no array.
        - `array`: O array que `filter()` foi chamado.
- **Exemplo de Uso:**
    
    - Aqui está um exemplo simples de como usar `filter()` para filtrar números pares de um array:

```
	const numeros = [1, 2, 3, 4, 5, 6];
	const numerosPares = numeros.filter(function(numero) {
    return numero % 2 === 0;
	});
	// Resultado: [2, 4, 6]
```
	
- **Encadeamento de Métodos:**
    
    - O método `filter()` pode ser encadeado com outros métodos de array, como `map()`, `reduce()`, `forEach()`, etc., para realizar operações mais complexas em um único pipeline.
- **Compatibilidade:**
    
    - O método `filter()` está disponível em todos os navegadores modernos e é compatível com todas as versões recentes de JavaScript.
- **Conclusão:**
    
    - O método `filter()` é uma ferramenta poderosa em JavaScript para filtrar elementos de um array com base em determinados critérios, permitindo a criação de novos arrays contendo apenas os elementos desejados.
*
## References
[[Callback em Javascript]]
[[O map no Javascript]]
[[Arrow Functions em Js]]
[[zettels/Como o JavaScript funciona|Como o JavaScript funciona]]
[[Programação funcional]]
*
=