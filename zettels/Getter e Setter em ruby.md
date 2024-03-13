120320242122
Status: #idea #Fleeting 
Tags: #Poo #Ruby 
# Getter e Setter em ruby
**O que são?**

Getters e setters são métodos especiais em Ruby que permitem controlar o acesso aos atributos de um objeto.

**Getters:**

- São métodos que recuperam o valor de um atributo.
- São gerados automaticamente quando você declara um atributo com `attr_accessor`.
- O nome do getter é o mesmo que o nome do atributo.

**Exemplo:**
```
class Pessoa
  attr_accessor :nome
end

pessoa1 = Pessoa.new("Ana")

# Getter em ação
nome = pessoa1.nome  # Output: "Ana"
```
**Setters:**

- São métodos que definem o valor de um atributo.
- São gerados automaticamente quando você declara um atributo com `attr_accessor`.
- O nome do setter é o mesmo que o nome do atributo, seguido de `=`.

**Exemplo:**
```
class Pessoa
  attr_accessor :nome
end

pessoa1 = Pessoa.new

# Setter em ação
pessoa1.nome = "Beatriz"

puts pessoa1.nome  # Output: "Beatriz"
```
**Atributos Públicos e Privados:**

- **Atributos públicos:** São acessíveis por qualquer código.
- **Atributos privados:** São acessíveis apenas dentro da classe em que foram declarados.

Para declarar um atributo como privado, utilize a palavra-chave `private` antes do nome do atributo:
```
class Pessoa
  attr_accessor :nome
  private :idade

  def initialize(nome, idade)
    @nome = nome
    @idade = idade
  end
end

pessoa1 = Pessoa.new("Ana", 25)

# Atributo público
puts pessoa1.nome  # Output: "Ana"

# Atributo privado - Erro de acesso
# puts pessoa1.idade  # Erro: `idade` é um método privado
```
**Benefícios:**

- **Encapsulamento:** Permite ocultar detalhes de implementação e proteger os dados internos do objeto.
- **Controle de acesso:** Permite controlar quais partes do código podem modificar os atributos do objeto.
- **Segurança:** Permite evitar alterações indesejadas nos dados do objeto.

**Lembre-se:**

- O uso de getters e setters pode tornar o código mais verboso.
- É importante usar o bom senso para determinar quais atributos devem ser públicos e quais devem ser privados.
- Atributos privados podem dificultar a depuração do código.
*
## References
[[[Poo em ruby]]]
[[Classe em ruby]]
*
