050320242315
Status: #idea #Fleeting 
Tags: #Programação #Poo 
# Princípio da Segregação da Interface (ISP)
**Definição:**

O **princípio da segregação da interface** (ISP) é um dos princípios SOLID que visa aumentar a **coesão**, **flexibilidade** e **reutilização** do código em projetos orientados a objetos (POO). O ISP afirma que:

**As interfaces devem ser pequenas e coesas, definindo apenas os métodos necessários para uma funcionalidade específica.**

**Explicação:**

Uma interface coesa é aquela que define um conjunto de métodos relacionados a uma única funcionalidade. Interfaces grandes e complexas tendem a ser menos coesas e mais difíceis de entender e usar.

**Exemplos de Casos de Uso:**

- **Calcular a área de figuras geométricas:** Uma interface `FiguraGeometrica` pode definir um método `calcularArea()`. As classes `Retangulo`, `Circulo` e `Triangulo` podem implementar essa interface para fornecer a funcionalidade de cálculo de área.
- **Validar dados de entrada:** Uma interface `ValidadorDados` pode definir um método `validar()`. As classes `ValidadorCPF`, `ValidadorEmail` e `ValidadorData` podem implementar essa interface para fornecer a funcionalidade de validação de dados específicos.
- **Enviar uma mensagem:** Uma interface `Mensageria` pode definir um método `enviar()`. As classes `Email` e `SMS` podem implementar essa interface para fornecer a funcionalidade de envio de mensagens por diferentes canais.

**Exemplo de Código:**
```
interface FiguraGeometrica:
    def calcular_area(self) -> float:


class Retangulo(FiguraGeometrica):
    def __init__(self, base: float, altura: float):
        self.base = base
        self.altura = altura

    def calcular_area(self) -> float:
        return self.base * self.altura


class Circulo(FiguraGeometrica):
    def __init__(self, raio: float):
        self.raio = raio

    def calcular_area(self) -> float:
        return math.pi * self.raio ** 2


# Exemplo de uso

retangulo = Retangulo(5, 10)
area_retangulo = retangulo.calcular_area()

circulo = Circulo(5)
area_circulo = circulo.calcular_area()

```
**Observações:**

- No exemplo acima, a interface `FiguraGeometrica` define um único método `calcularArea()`.
- As classes `Retangulo` e `Circulo` implementam a interface `FiguraGeometrica` para fornecer a funcionalidade de cálculo de área.
- Interfaces pequenas e coesas são mais fáceis de entender e usar.
- Interfaces coesas são mais flexíveis e reutilizáveis.

**Conclusão:**

O ISP é um princípio fundamental em POO que pode ajudar a escrever código mais coeso, flexível e reutilizável. Ao seguir o ISP, você pode aumentar a qualidade do seu código e melhorar a produtividade da sua equipe.
*
## References
[[Princípio da Substituição de Liskov (LSP)]]
[[Princípio Aberto-Fechado (OCP)]]
[[Princípio SOLID]]
[[Princípio da Responsabilidade Única (SRP)]]s
*
