160220241258
Status: #idea
Tags: 
# Canais em Golang

Canais são um tipo de canal de comunicação em Golang que permite enviar e receber valores entre goroutines.

**Funcionalidades:**

- **make(chan T):** Cria um canal com tipo `T`.
- **len(c):** Retorna o número de elementos no canal.
- **cap(c):** Retorna a capacidade máxima do canal.
- **c <- v:** Envia o valor `v` para o canal `c`.
- **v := <-c:** Recebe um valor do canal `c` e o armazena na variável `v`.

**Exemplo de uso:**

```
func main() {
  canal := make(chan int)

  go func() {
    // Envia um valor para o canal
    canal <- 10
  }()

  valor := <-canal

  // O valor 10 foi recebido do canal
  fmt.Println("Valor recebido:", valor)
}

```
**Benefícios:**

- Comunicação eficiente entre goroutines.
- Permite implementar paralelismo e comunicação assíncrona.
- Facilita o desenvolvimento de programas mais complexos.

**Limitações:**

- Canais sem buffer podem causar bloqueio se uma goroutine tentar enviar um valor para um canal cheio.
- Canais com buffer podem levar a um uso excessivo de memória se o buffer for muito grande.


**Observações:**

- Canais são uma ferramenta fundamental para comunicação entre goroutines em Golang.
- É importante usar canais de forma adequada para evitar bloqueios e garantir a execução correta do seu programa.
*
## References
[[Wait group em golang]]
*
