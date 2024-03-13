120320242114
Status: #idea #Fleeting 
Tags:  #poo #Programação #Ruby 
# Classe em ruby
## Classes em Ruby (Nota Zettel)

**O que são classes?**

Classes em Ruby são modelos para a criação de objetos. Elas definem a estrutura e o comportamento dos objetos que serão criados a partir delas, como seus atributos (características) e métodos (comportamentos).

**Criação de Classes:**

Para criar uma classe em Ruby, utilize a palavra-chave `class` seguida do nome da classe:
```
class Pessoa
  # Atributos e métodos da classe Pessoa
end
```
**Atributos:**

Atributos definem as características dos objetos. São variáveis que armazenam informações específicas de cada objeto.

Para declarar um atributo em uma classe, utilize a palavra-chave `attr_accessor` seguida do nome do atributo:
```
class Pessoa
  attr_accessor :nome, :idade
end
```
Isso cria métodos de acesso `#nome` e `#nome=` para ler e escrever o valor do atributo `nome`, e métodos de acesso `#idade` e `#idade=` para ler e escrever o valor do atributo `idade`.

**Métodos:**

Métodos definem os comportamentos dos objetos. São ações que os objetos podem realizar.

Para declarar um método em uma classe, utilize a palavra-chave `def` seguida do nome do método e seus parâmetros (entre parênteses):
```
class Pessoa
  def falar
    puts "Olá, meu nome é #{@nome} e tenho #{@idade} anos."
  end
end

```
**Criando Objetos:**

Para criar um objeto a partir de uma classe, utilize o operador `new`:
```
pessoa1 = Pessoa.new("Ana", 25)
```
**Acessando Atributos e Métodos:**

Para acessar os atributos e métodos de um objeto, utilize a sintaxe de ponto:
```
puts pessoa1.nome  # Output: "Ana"
pessoa1.falar  # Output: "Olá, meu nome é Ana e tenho 25 anos."
```
**Herança:**

Herança permite que uma classe herde atributos e métodos de outra classe. Isso facilita o reuso de código e a organização de classes em uma hierarquia.

Para definir herança, utilize a palavra-chave `<` seguida do nome da classe pai:
```
class Funcionario < Pessoa
  # Atributos e métodos específicos de Funcionário
end
```

**Polimorfismo:**

Polimorfismo permite que diferentes objetos respondam à mesma mensagem de maneira diferente, de acordo com sua classe.

Exemplo:
```
class Animal
  def falar
    puts "Som genérico de animal"
  end
end

class Cachorro < Animal
  def falar
    puts "Au au!"
  end
end

class Gato < Animal
  def falar
    puts "Miau!"
  end
end

# Polimorfismo em ação
cachorro1 = Cachorro.new
gato1 = Gato.new

cachorro1.falar  # Output: "Au au!"
gato1.falar  # Output: "Miau!"
```

*
## References
[[Poo em ruby]]
*
