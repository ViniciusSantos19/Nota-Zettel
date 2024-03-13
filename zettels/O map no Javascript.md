110220241741
Status: #idea #Fleeting 
Tags: #Programação #Javascript #Funcional 
# O map no Javascript
O método `map()` é uma função de array em JavaScript que cria um novo array com os resultados de uma função de callback aplicada a cada elemento do array original. É uma maneira eficaz e elegante de transformar os elementos de um array sem modificar o array original.

### Detalhes 

- **uncionamento:**
    
    - O método `map()` itera sobre cada elemento do array original e chama uma função de callback fornecida como argumento. O valor retornado pela função de callback é armazenado em um novo array.
- **Sintaxe:**
    
    - A sintaxe básica do método `map()` é a seguinte:

	```
	const novoArray = arrayOriginal.map(function(elemento) {
    // Operações de transformação
    return novoElemento;
});
- **Callback:**
    
    - A função de callback passada para `map()` pode receber até três argumentos: `elemento`, `índice` e `array`.
        - `elemento`: O elemento atual sendo processado no array.
        - `índice`: O índice do elemento atual sendo processado no array.
        - `array`: O array que `map()` foi chamado.
- **Imutabilidade:**
    
    - O método `map()` retorna um novo array, mantendo o array original intacto. Isso ajuda a garantir a imutabilidade dos dados, um conceito importante na programação funcional.
- **Exemplo de Uso:**
    
    - Aqui está um exemplo simples de como usar `map()` para duplicar todos os elementos de um array:

```
const numeros = [1, 2, 3, 4, 5];
const duplicados = numeros.map(function(numero) {
    return numero * 2;
});
// Resultado: [2, 4, 6, 8, 10]

```
- **Encadeamento de Métodos:**
    
    - O método `map()` pode ser encadeado com outros métodos de array, como `filter()`, `reduce()`, `forEach()`, etc., para realizar operações mais complexas em um único pipeline.
- **Compatibilidade:**
    
    - O método `map()` está disponível em todos os navegadores modernos e é compatível com todas as versões recentes de JavaScript.
- **Conclusão:**
    
    - O método `map()` é uma ferramenta poderosa em JavaScript para transformar e manipular arrays de forma declarativa e funcional. Sua capacidade de criar um novo array baseado nos elementos de um array original torna-o valioso em uma variedade de situações de programação.
*
## References
[[zettels/Como o JavaScript funciona|Como o JavaScript funciona]]
[[Programação funcional]]
[[Callback em Javascript]]
*
