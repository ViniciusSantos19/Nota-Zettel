120320242107
Status: #idea #Fleeting 
Tags: #
# Poo em ruby
**O que é?**

A Programação Orientada a Objetos (POO) em Ruby é um paradigma de programação que organiza o código em torno de objetos, que são entidades que possuem características (atributos) e comportamentos (métodos).

**Conceitos Básicos:**

- **Classe:** Define um modelo para a criação de objetos, com seus atributos e métodos.
- **Objeto:** Instância de uma classe, com seus próprios valores de atributos e comportamentos.
- **Encapsulamento:** Esconde os detalhes internos de um objeto, expondo apenas uma interface pública para interação.
- **Herança:** Permite que uma classe herde atributos e métodos de outra classe, promovendo reuso de código.
- **Polimorfismo:** Permite que diferentes objetos respondam à mesma mensagem de maneira diferente, de acordo com sua classe.

**Benefícios da POO:**

- **Modularidade:** Permite dividir o código em módulos menores e reutilizáveis.
- **Reuso de código:** Facilita o compartilhamento de código entre diferentes classes.
- **Manutenabilidade:** Torna o código mais fácil de entender, modificar e manter.
- **Extensibilidade:** Facilita a adição de novas funcionalidades ao código.

**Exemplos em Ruby:**
```
# Classe Pessoa
class Pessoa
  attr_accessor :nome, :idade

  def initialize(nome, idade)
    @nome = nome
    @idade = idade
  end

  def falar
    puts "Olá, meu nome é #{@nome} e tenho #{@idade} anos."
  end
end

# Criando um objeto Pessoa
pessoa1 = Pessoa.new("Ana", 25)

# Acessando o atributo nome
puts pessoa1.nome  # Output: "Ana"

# Chamando o método falar
pessoa1.falar  # Output: "Olá, meu nome é Ana e tenho 25 anos."
```

*
## References
[[Classe em ruby]]
*
