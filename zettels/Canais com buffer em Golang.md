160220241303
Status: #idea #Fleeting 
Tags: #Programação #Golang #Concorrência 
# Canais com buffer em Golang
Canais com buffer em Golang são canais que possuem uma capacidade máxima de elementos que podem ser armazenados antes de serem bloqueados.

**Funcionalidades:**

- **make(chan T, n):** Cria um canal com tipo `T` e capacidade `n`.
- **len(c):** Retorna o número de elementos no canal.
- **cap(c):** Retorna a capacidade máxima do canal.
- **c <- v:** Envia o valor `v` para o canal `c`. Se o canal estiver cheio, a goroutine será bloqueada até que haja espaço disponível.
- **v := <-c:** Recebe um valor do canal `c` e o armazena na variável `v`. Se o canal estiver vazio, a goroutine será bloqueada até que um valor seja enviado.

**Exemplo de uso:**
```
func main() {
  canal := make(chan int, 2)

  go func() {
    // Envia dois valores para o canal
    canal <- 10
    canal <- 20
  }()

  valor1 := <-canal
  valor2 := <-canal

  // Os valores 10 e 20 foram recebidos do canal
  fmt.Println("Valor 1:", valor1)
  fmt.Println("Valor 2:", valor2)
}
```
**Benefícios:**

- Evita bloqueios quando o canal está cheio.
- Permite que várias goroutines enviem valores para o canal sem esperar.
- Facilita o desenvolvimento de programas mais robustos.

**Limitações:**

- Canais com buffer grande podem levar a um uso excessivo de memória.
- Se a capacidade do buffer for muito pequena, o canal pode ser bloqueado com frequência.


**Observações:**

- Canais com buffer são uma ferramenta útil para evitar bloqueios em programas Go.
- É importante escolher a capacidade do buffer de acordo com as necessidades do seu programa.
*
## References
[[Canais em Golang]]
[[Wait group em golang]]
*
