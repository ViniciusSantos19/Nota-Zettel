120320242053
Status: #idea #Fleeting 
Tags:  #Ruby #Enumerables 
# Array em ruby
**O que são?**

Arrays em Ruby são estruturas de dados que armazenam coleções ordenadas de elementos. São versáteis e podem armazenar qualquer tipo de objeto, como números, strings, hashes, e até outros arrays.

**Criação:**

- `[]`: Criar um array vazio.
- `[elemento1, elemento2, ...]`: Criar um array com elementos predefinidos.

**Exemplos:**
```
# Array vazio
arr = []

# Array com elementos
arr = [1, "banana", {nome: "Ana"}, [1, 2, 3]]
```
**Métodos Úteis:**

- `#length`: Retorna o número de elementos no array.
- `#[]`: Acessa um elemento pelo índice (começando em 0).
- `#<<`: Adiciona um elemento ao final do array.
- `#.push`: Adiciona um elemento ao final do array (sinônimo de `#<<`).
- `#.unshift`: Adiciona um elemento ao início do array.
- `#.pop`: Remove o último elemento do array.
- `#.shift`: Remove o primeiro elemento do array.
- `#include?`: Verifica se um elemento existe no array.
- `#index(elemento)`: Retorna o índice da primeira ocorrência do elemento.
- `#each`: Itera sobre cada elemento do array, executando um bloco de código.

**Exemplos:**
```
arr = [1, 2, 3, 4, 5]

# Acessando o terceiro elemento
puts arr[2]  # Output: 3

# Adicionando um elemento ao final
arr << 6
puts arr  # Output: [1, 2, 3, 4, 5, 6]

# Removendo o primeiro elemento
arr.shift
puts arr  # Output: [2, 3, 4, 5, 6]

# Verificando se um elemento existe
puts arr.include?(4)  # Output: true

# Iterando sobre cada elemento e dobrando seu valor
arr.each { |number| number *= 2 }
puts arr  # Output: [4, 6, 8, 10, 12]
```

*
## References
Documentação oficial do Ruby: [https://ruby-doc.org/core/Array.html](https://ruby-doc.org/core/Array.html)
[[Ruby enumerables]]
*
