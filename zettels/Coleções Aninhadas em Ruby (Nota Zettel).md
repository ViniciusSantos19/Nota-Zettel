120320242103
Status: #idea #Fleeting 
Tags: #Ruby #Programação 
# Coleções Aninhadas em Ruby (Nota Zettel)
**O que são?**

Coleções aninhadas em Ruby são estruturas de dados que armazenam outras coleções dentro delas. Isso significa que você pode ter arrays de arrays, arrays de hashes, hashes de arrays e hashes de hashes, criando estruturas de dados complexas e multidimensionais.

**Exemplos:**

- **Array de arrays:**
```
arr = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

- **Array de hashes:**
```
arr = [{nome: "Ana", idade: 25}, {nome: "João", idade: 30}]
```
- **Hash de arrays:**

```
hash = {"frutas" => ["banana", "maçã", "laranja"], "cores" => ["azul", "verde", "vermelho"]}
```
- **Hash de hashes:**
```
hash = {"pessoa1" => {nome: "Ana", idade: 25}, "pessoa2" => {nome: "João", idade: 30}}
```
**Acesso e Manipulação:**

Para acessar e manipular elementos em coleções aninhadas, você usa a mesma sintaxe de acesso a arrays e hashes, mas com aninhamento:

```
# Acessando o segundo elemento do segundo array
arr[1][1]  # Output: 5

# Acessando a idade da primeira pessoa no hash de hashes
hash["pessoa1"]["idade"]  # Output: 25

# Iterando sobre cada array no array de arrays
arr.each do |sub_arr|
  sub_arr.each do |element|
    puts element
  end
end
```
**Resolução de Problemas:**

As coleções aninhadas são ferramentas poderosas para organizar e manipular dados complexos.

**Exemplos de resolução de problemas:**

- **Analisar dados de uma planilha:** Um array de arrays pode armazenar as linhas e colunas da planilha.
- **Criar um catálogo de produtos:** Um hash de hashes pode armazenar informações sobre cada produto, como nome, preço e descrição.
- **Simular um jogo de tabuleiro:** Um array de arrays pode representar o tabuleiro, e um hash de hashes pode armazenar as informações dos jogadores.

**Dicas:**

- Use nomes descritivos para as variáveis e coleções para facilitar a compreensão do código.
- Utilize métodos de iteração como `#each` para percorrer as coleções aninhadas de forma eficiente.
- Documente seu código para explicar a lógica e o propósito das coleções aninhadas.

*
## References
[[Array em ruby]]
[[Hash em ruby]]
[[Ruby enumerables]]
*
