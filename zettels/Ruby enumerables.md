120320242040
Status: #idea #Fleeting 
Tags: #Ruby #Programação #Enumerables
# Ruby enumerables
Enumerables são um módulo básico e poderoso do Ruby que fornece métodos para iterar sobre coleções de objetos. Classes como `Array`, `Hash`, `Set` e outras herdam esse módulo, permitindo a utilização de métodos convenientes para processar seus elementos.

**Benefícios:**

- **DRY (Don't Repeat Yourself):** Evitam a repetição de código para iterar sobre coleções.
- **Concisão:** Oferecem uma sintaxe limpa e expressiva para manipular coleções.
- **Flexibilidade:** Permitem a aplicação de lógica personalizada a cada elemento usando blocos de código.

**Alguns métodos comuns:**

- `each`: Itera sobre cada elemento da coleção, podendo executar um bloco de código para cada um.
- `map`: Transforma cada elemento da coleção usando um bloco de código e retorna um novo array com os resultados.
- `select`: Filtra a coleção, retornando um novo array contendo somente os elementos que atendem a uma condição definida em um bloco de código.
- `find`: Localiza o primeiro elemento que satisfaz uma condição (opcionalmente, retorna `nil` se não encontrar).
- `all?`: Verifica se todos os elementos da coleção atendem a uma condição (retorna `true` se todos atendem, `false` caso contrário).
- `any?`: Verifica se pelo menos um elemento da coleção atende a uma condição (retorna `true` se algum atende, `false` caso contrário).
- `count`: Conta o número de elementos na coleção ou o número de elementos que atendem a uma condição (opcional).

### Exemplo
```
numbers = [1, 2, 3, 4, 5]

# Duplicando cada número:
doubled_numbers = numbers.map { |number| number * 2 }

# Filtrando números pares:
even_numbers = numbers.select { |number| number.even? }

# Somando todos os números:
total_sum = numbers.reduce(0) { |sum, number| sum + number }

puts doubled_numbers  # Output: [2, 4, 6, 8, 10]
puts even_numbers    # Output: [2, 4]
puts total_sum       # Output: 15
```



*
## References
- Documentação oficial do Ruby: [https://ruby-doc.org/core/Enumerable.html](https://ruby-doc.org/core/Enumerable.html)
- Guia completo sobre Enumerables (em inglês): [https://medium.com/@mckenziefiege/common-ruby-enumerable-methods-guide-2a9cb2880415](https://medium.com/@mckenziefiege/common-ruby-enumerable-methods-guide-2a9cb2880415)
	[[Array em ruby]]
*
