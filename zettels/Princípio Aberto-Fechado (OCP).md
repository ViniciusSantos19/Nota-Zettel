050320242302
Status: #idea
Tags: 
# Princípio Aberto-Fechado (OCP)
**Definição:**

O **princípio aberto-fechado** (OCP) é um dos princípios SOLID que visa aumentar a **flexibilidade** e **extensibilidade** do código em projetos orientados a objetos (POO). O OCP afirma que:

**As entidades de software (classes, módulos, funções, etc.) devem estar abertas para extensão, mas fechadas para modificação.**

**Explicação:**

Uma entidade de software aberta para extensão pode ser modificada sem a necessidade de alterar o código existente. Isso significa que novos comportamentos podem ser adicionados sem modificar o código das classes existentes. Uma entidade de software fechada para modificação significa que seu código não deve ser modificado após sua criação.

**Exemplos de Casos de Uso:**

- **Adicionar um novo tipo de pagamento:** Um sistema de e-commerce deve ser capaz de aceitar novos tipos de pagamento sem a necessidade de modificar o código existente.
- **Adicionar um novo idioma:** Um aplicativo deve ser capaz de ser traduzido para novos idiomas sem a necessidade de modificar o código existente.
- **Adicionar um novo tipo de relatório:** Um sistema de BI deve ser capaz de gerar novos tipos de relatórios sem a necessidade de modificar o código existente.

**Exemplo de Código:**
```
class Calculadora:
    def __init__(self, operacao):
        self.operacao = operacao

    def calcular(self, a, b):
        if self.operacao == "+":
            return a + b
        elif self.operacao == "-":
            return a - b
        elif self.operacao == "*":
            return a * b
        elif self.operacao == "/":
            return a / b


class Soma(Calculadora):
    def __init__(self):
        super().__init__("+")


class Subtracao(Calculadora):
    def __init__(self):
        super().__init__("-")


class Multiplicacao(Calculadora):
    def __init__(self):
        super().__init__("*")


class Divisao(Calculadora):
    def __init__(self):
        super().__init__("/")


# Exemplo de uso

soma = Soma()
resultado = soma.calcular(10, 20)

subtracao = Subtracao()
resultado = subtracao.calcular(20, 10)

multiplicacao = Multiplicacao()
resultado = multiplicacao.calcular(10, 2)

divisao = Divisao()
resultado = divisao.calcular(10, 2)

```
**Observações:**

- No exemplo acima, a classe `Calculadora` é aberta para extensão através da herança.
- Novas classes podem ser criadas para implementar novos tipos de operações sem a necessidade de modificar o código da classe `Calculadora`.
- As classes `Soma`, `Subtracao`, `Multiplicacao` e `Divisao` são exemplos de classes que extendem a classe `Calculadora`.

**Conclusão:**

O OCP é um princípio fundamental em POO que pode ajudar a escrever código mais flexível e extensível. Ao seguir o OCP, você pode aumentar a capacidade de adaptação do seu código às novas necessidades do seu projeto.
*
## References
[[Princípio SOLID]]
[[Princípio da Responsabilidade Única (SRP)]]
*
