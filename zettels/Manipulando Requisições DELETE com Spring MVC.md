260320242215
Status: #idea #Fleeting 
Tags: #Programação  #Spring #web 
# Manipulando Requisições DELETE com Spring MVC
Em aplicações RESTful, a eliminação de recursos é uma operação comum e necessária. Spring MVC facilita essa tarefa por meio da anotação `@DeleteMapping`, especificamente projetada para lidar com requisições HTTP DELETE. Vamos explorar como implementar a funcionalidade de deletar um recurso, como um pedido (`order`), em uma API REST utilizando Spring MVC.

#### Exemplo de Uso do @DeleteMapping

Quando um cliente decide que um recurso não é mais necessário, ele pode solicitar sua remoção enviando uma requisição DELETE. No Spring MVC, o tratamento dessas requisições é realizado de forma declarativa com a anotação `@DeleteMapping`. A seguir, apresentamos um exemplo de método de controlador para deletar um recurso de pedido baseado em seu identificador:
```
@DeleteMapping("/{orderId}")
@ResponseStatus(HttpStatus.NO_CONTENT)
public void deleteOrder(@PathVariable("orderId") Long orderId) {
    try {
        repo.deleteById(orderId);
    } catch (EmptyResultDataAccessException e) {
        // Tratamento de exceção opcional
    }
}
```
Neste exemplo, o método `deleteOrder` é designado para responder a requisições DELETE para o caminho `/orders/{orderId}`. A variável de caminho `{orderId}` indica o identificador do pedido a ser deletado. O método então chama `deleteById` do repositório, passando o identificador do pedido.

#### Considerações Importantes

- **ResponseStatus**: O método está anotado com `@ResponseStatus(HttpStatus.NO_CONTENT)`, indicando que, se a operação for bem-sucedida, a resposta HTTP será 204 (NO CONTENT). Isso é apropriado para operações DELETE, onde tipicamente não há conteúdo a retornar após a remoção do recurso.
- **Tratamento de Exceções**: No exemplo, a exceção `EmptyResultDataAccessException` é capturada e não é feito nenhum tratamento. Isso se baseia na lógica de que tentar deletar um recurso inexistente é uma operação idempotente, resultando no mesmo estado final desejado: o recurso não existe. Alternativamente, poderia-se retornar um status HTTP diferente (como 404 NOT FOUND) se a preferência for informar explicitamente ao cliente que o recurso não foi encontrado.

#### Implementação e Design da API

A utilização de `@DeleteMapping` complementa as outras anotações de mapeamento do Spring MVC (`@GetMapping`, `@PostMapping`, `@PutMapping`, e `@PatchMapping`), permitindo um design de API RESTful completo e intuitivo. Essa abordagem declarativa simplifica a implementação de operações CRUD (Criar, Ler, Atualizar, Deletar), mantendo o código do controlador organizado e facilmente compreensível.

Este exemplo ilustra não apenas como implementar a funcionalidade de deletar recursos em uma API REST com Spring MVC, mas também destaca práticas importantes como o uso adequado de status HTTP e o tratamento de exceções. A habilidade de diferenciar quando e como informar ao cliente sobre o sucesso ou falha de uma operação de deleção é crucial para o desenvolvimento de APIs robustas e user-friendly.
*
## References
[[Entendendo PUT vs PATCH no Spring Data REST]]
[[Manipulação de Dados em REST APIs com Spring MVC]]
[[Controladores RESTful em Spring MVC]]
*
