050320242247
Status: #idea  #Fleeting 
Tags: #Programação #Poo
# Princípio da Responsabilidade Única (SRP)
**Definição:**

O **princípio da responsabilidade única** (SRP) é um dos princípios SOLID que visa aumentar a **coesão**, **flexibilidade** e **manutenabilidade** do código em projetos orientados a objetos (POO). O SRP afirma que:

**Uma classe deve ter apenas uma única responsabilidade.**

**Explicação:**

Uma classe com uma única responsabilidade é mais fácil de entender, modificar e testar. Ela também é mais flexível e reutilizável, pois seu foco é bem definido. Classes com múltiplas responsabilidades tendem a ser mais complexas, menos coesas e mais propensas a erros.

**Exemplos de Casos de Uso:**

- **Validar dados de entrada:** Uma classe responsável por validar dados de entrada deve ter apenas essa responsabilidade. Ela não deve se preocupar com a formatação dos dados ou com o que fazer com os dados após a validação.
- **Calcular o preço de um produto:** Uma classe responsável por calcular o preço de um produto deve ter apenas essa responsabilidade. Ela não deve se preocupar com a exibição do preço ou com o armazenamento do preço no banco de dados.
- **Enviar um e-mail:** Uma classe responsável por enviar um e-mail deve ter apenas essa responsabilidade. Ela não deve se preocupar com a formatação do e-mail ou com o conteúdo do e-mail.

**Exemplo de Código:**
```
class Pessoa:
    def __init__(self, nome, idade):
        self.nome = nome
        self.idade = idade

    def get_nome(self):
        return self.nome

    def get_idade(self):
        return self.idade


class ValidadorPessoa:
    def __init__(self, pessoa):
        self.pessoa = pessoa

    def validar(self):
        if not self.pessoa.nome:
            raise ValueError("Nome inválido")

        if not self.pessoa.idade:
            raise ValueError("Idade inválida")


class CalculadorPreco:
    def __init__(self, produto):
        self.produto = produto

    def calcular(self):
        return self.produto.preco_base * (1 + self.produto.imposto)


class EnviadoEmail:
    def __init__(self, email):
        self.email = email

    def enviar(self):
        # ...


# Exemplo de uso

pessoa = Pessoa("João", 30)

validador = ValidadorPessoa(pessoa)
validador.validar()

calculador = CalculadorPreco(produto)
preco = calculador.calcular()

enviado = EnviadoEmail(email)
enviado.enviar()

```
**Observações:**

- No exemplo acima, cada classe tem uma única responsabilidade.
- As classes são coesas e fáceis de entender.
- As classes são flexíveis e reutilizáveis.
- O código é mais robusto e menos propenso a erros.

**Conclusão:**

O SRP é um princípio fundamental em POO que pode ajudar a escrever código mais limpo, robusto e fácil de manter. Ao seguir o SRP, você pode melhorar a qualidade do seu código e aumentar a produtividade da sua equipe.
*
## References
[[Princípio SOLID]]
*
