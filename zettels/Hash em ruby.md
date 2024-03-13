120320242058
Status: #idea #Fleeting 
Tags: #Programação #Ruby  
# Hash em ruby
**O que são?**

Hashes em Ruby são estruturas de dados que armazenam pares de chave-valor. São como dicionários, onde cada chave está associada a um valor específico. As chaves podem ser strings, símbolos, números ou outros objetos, enquanto os valores podem ser qualquer tipo de dado em Ruby.

**Criação:**

- `{}`: Criar um hash vazio.
- `{chave1 => valor1, chave2 => valor2, ...}`: Criar um hash com pares de chave-valor predefinidos.

**Exemplos:**
```
# Hash vazio
hash = {}

# Hash com pares de chave-valor
hash = {"nome" => "Ana", "idade" => 25, "cidade" => "Salvador"}
```
**Métodos Úteis:**

- `#length`: Retorna o número de pares de chave-valor no hash.
- `#[]`: Acessa um valor pela chave.
- `#[]=(chave, valor)`: Define um valor para uma chave específica.
- `#has_key?(chave)`: Verifica se uma chave existe no hash.
- `#each`: Itera sobre cada par de chave-valor do hash, executando um bloco de código.
- `#merge(hash2)`: Combina dois hashes em um único hash.

** Exemplos**

```
hash = {"nome" => "Ana", "idade" => 25}

# Acessando o valor da chave "nome"
puts hash["nome"]  # Output: "Ana"

# Definindo um valor para a chave "email"
hash["email"] = "ana@exemplo.com"
puts hash  # Output: {"nome" => "Ana", "idade" => 25, "email" => "ana@exemplo.com"}

# Verificando se a chave "cidade" existe
puts hash.has_key?("cidade")  # Output: false

# Iterando sobre cada par chave-valor e imprimindo
hash.each do |chave, valor|
  puts "#{chave}: #{valor}"
end

# Combinando dois hashes
hash2 = {"telefone" => "11 9999-9999"}
combined_hash = hash.merge(hash2)
puts combined_hash  # Output: {"nome" => "Ana", "idade" => 25, "email" => "ana@exemplo.com", "telefone" => "11 9999-9999"}
```

*
## References
- Documentação oficial do Ruby: [https://ruby-doc.org/core/Hash.html](https://ruby-doc.org/core/Hash.html)

	[[Ruby enumerables]]
	[[Array em ruby]]
*
