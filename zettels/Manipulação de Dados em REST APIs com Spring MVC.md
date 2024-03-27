260320242159
Status: #idea #Fleeting 
Tags:  #Programação #web #Spring 
# Manipulação de Dados em REST APIs com Spring MVC
#### Contexto

Na construção de REST APIs com Spring MVC, além da capacidade de recuperar dados (como visto com `@GetMapping`), é crucial poder manipular (criar e atualizar) dados no servidor. O Spring MVC facilita isso com anotações específicas como `@PostMapping`, `@PutMapping`, e `@PatchMapping`, cada uma alinhada a um método HTTP específico para a manipulação de dados de forma semântica.

#### Criação de Recursos com `@PostMapping`

- **Uso**: Para criar novos recursos no servidor.
- **Anotação**: `@PostMapping`
- **Exemplo de Uso**:
```
@PostMapping(consumes="application/json")
@ResponseStatus(HttpStatus.CREATED)
public Taco postTaco(@RequestBody Taco taco) {
    return tacoRepo.save(taco);
}
```
- **Detalhes**:
    - `@PostMapping` indica que o método lida com requisições POST.
    - `consumes="application/json"` especifica que o método aceita apenas requisições com corpo em formato JSON.
    - `@RequestBody` anotação no parâmetro `Taco taco` indica que o corpo da requisição POST deve ser convertido para um objeto `Taco`.
    - `@ResponseStatus(HttpStatus.CREATED)` informa que, em caso de sucesso, o status HTTP 201 (Created) deve ser retornado, significando a criação de um recurso.

#### Atualização de Recursos com `@PutMapping` e `@PatchMapping`

Enquanto `@PostMapping` é comumente usado para a criação de novos recursos, `@PutMapping` e `@PatchMapping` são empregados para atualizações, seguindo a semântica dos métodos HTTP PUT e PATCH, respectivamente.

- **PUT vs PATCH**:
    
    - **PUT**: Usado para atualizar um recurso existente integralmente.
    - **PATCH**: Usado para atualizar parcialmente um recurso existente.
- **Exemplo de Uso** (Não fornecido diretamente neste trecho, mas conceitualmente):
```
@PutMapping(path = "/{id}", consumes = "application/json")
public ResponseEntity<Taco> updateTaco(@PathVariable("id") Long id, @RequestBody Taco updatedTaco) {
    // Lógica para atualizar um Taco existente, substituindo-o completamente.
    // Retornar ResponseEntity com o status apropriado.
}

@PatchMapping(path = "/{id}", consumes = "application/json")
public ResponseEntity<Taco> partialUpdateTaco(@PathVariable("id") Long id, @RequestBody Map<String, Object> updates) {
    // Lógica para aplicar uma atualização parcial em um Taco existente.
    // Retornar ResponseEntity com o status apropriado.
}
```
#### Importância

A clareza na escolha do método HTTP e na semântica do endpoint promove uma interface de programação mais intuitiva e aderente aos padrões REST, facilitando a integração e a manutenção por desenvolvedores que consomem a API.
*
## References
[[Controladores RESTful em Spring MVC]]
*
