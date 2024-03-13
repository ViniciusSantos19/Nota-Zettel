160220241241
Status: #idea #Fleeting 
Tags: #Programação  #Concorrência #Golang
# Wait group em golang
**Descrição:**

Wait Group é um tipo de sincronização em Golang usado para esperar que um grupo de goroutines termine sua execução antes de continuar.

**Funcionalidades:**

- **Add(n):** Incrementa o contador interno da Wait Group em `n`.
- **Done():** Decrementa o contador interno da Wait Group em 1.
- **Wait():** Bloqueia a execução da goroutine até que o contador interno da Wait Group chegue a 0.

**Exemplo de uso:**

```
func main() {
  var wg sync.WaitGroup
  wg.Add(2)

  go func() {
    // Tarefa 1
    wg.Done()
  }()

  go func() {
    // Tarefa 2
    wg.Done()
  }()

  wg.Wait()

  // As tarefas 1 e 2 terminaram
  fmt.Println("Todas as tarefas finalizadas!")
}

```
**Benefícios:**

- Sincronização eficiente de goroutines.
- Evita que a main goroutine termine antes que todas as goroutines filhas terminem.
- Facilita a implementação de paralelismo em Golang.

**Limitações:**

- Não é adequado para sincronização entre goroutines que se comunicam entre si.
- Pode levar a um deadlock se o contador da Wait Group for incrementado, mas nunca decrementado.

**Observações:**

- Wait Group é uma ferramenta poderosa para sincronizar goroutines em Golang.
- É importante usar Wait Group de forma adequada para evitar deadlocks e garantir a execução correta do seu programa.

*
## References
*
