050320242311
Status: #idea
Tags: 
# Princípio da Substituição de Liskov (LSP)
**Definição:**

O **princípio da substituição de Liskov** (LSP) é um dos princípios SOLID que visa aumentar a **robustez** e **confiabilidade** do código em projetos orientados a objetos (POO). O LSP afirma que:

**Se `S` é um subtipo de `T`, então objetos de tipo `S` podem ser substituídos por objetos de tipo `T` sem afetar o comportamento correto do programa.**

**Explicação:**

Em outras palavras, se uma classe herda de outra classe, ela deve ser capaz de substituir a classe base em qualquer contexto sem que o programa apresente erros. Isso significa que a subclasse deve ter o mesmo comportamento da classe base, além de poder ter comportamentos adicionais.

**Exemplos de Casos de Uso:**

- **Calcular a área de figuras geométricas:** Uma classe `FiguraGeometrica` pode ter um método `calcularArea()`. As subclasses `Retangulo`, `Circulo` e `Triangulo` podem sobrescrever esse método para calcular a área específica de cada figura.
- **Validar dados de entrada:** Uma classe `ValidadorDados` pode ter um método `validar()`. As subclasses `ValidadorCPF`, `ValidadorEmail` e `ValidadorData` podem sobrescrever esse método para validar dados específicos.
- **Enviar uma mensagem:** Uma classe `Mensageria` pode ter um método `enviar()`. As subclasses `Email` e `SMS` podem sobrescrever esse método para enviar mensagens por diferentes canais.

**Exemplo de Código:**
```
class FiguraGeometrica:
    def calcular_area(self):
        raise NotImplementedError


class Retangulo(FiguraGeometrica):
    def __init__(self, base, altura):
        self.base = base
        self.altura = altura

    def calcular_area(self):
        return self.base * self.altura


class Circulo(FiguraGeometrica):
    def __init__(self, raio):
        self.raio = raio

    def calcular_area(self):
        return math.pi * self.raio ** 2


# Exemplo de uso

retangulo = Retangulo(5, 10)
area_retangulo = retangulo.calcular_area()

circulo = Circulo(5)
area_circulo = circulo.calcular_area()

```
**Observações:**

- No exemplo acima, as classes `Retangulo` e `Circulo` herdam da classe `FiguraGeometrica`.
- As classes `Retangulo` e `Circulo` sobrescrevem o método `calcular_area()` para calcular a área específica de cada figura.
- Objetos de tipo `Retangulo` e `Circulo` podem ser substituídos por objetos de tipo `FiguraGeometrica` sem afetar o comportamento correto do programa.

**Conclusão:**

O LSP é um princípio fundamental em POO que pode ajudar a escrever código mais robusto e confiável. Ao seguir o LSP, você pode aumentar a qualidade do seu código e evitar erros de software.
*
## References
[[Princípio Aberto-Fechado (OCP)]]
[[Princípio SOLID]]
[[Princípio da Responsabilidade Única (SRP)]]
*
