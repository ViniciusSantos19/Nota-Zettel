260320242150
Status: #idea #Fleeting 
Tags:  #Programação #Spring #web 
# Controladores RESTful em Spring MVC
- **Controladores RESTful vs. Websites:** Similaridade no atendimento de requisições HTTP, diferindo principalmente no tipo de resposta: enquanto websites respondem geralmente em HTML, APIs REST respondem em formatos orientados a dados, como JSON ou XML.
- **Anotações do Spring MVC para Requisições HTTP:**
    - `@GetMapping` para requisições GET, usualmente para leitura de dados.
    - `@PostMapping` para requisições POST, geralmente para criação de recursos.
    - `@PutMapping` e `@PatchMapping` para atualizações com PUT e PATCH, respectivamente.
    - `@DeleteMapping` para deleção de recursos.
    - `@RequestMapping` para tratamento genérico de requisições, com método HTTP especificado pelo atributo `method`.
- **Criação de um Endpoint REST para Tacos Recentes:**
    - Utilização do `@RestController` e `@GetMapping` para criar um endpoint que responde a requisições GET para `/api/tacos` com parâmetro “recent”, retornando uma lista de designs de tacos recentemente criados.
    - A importância do `@RestController` para indicar que o valor de retorno dos métodos manipuladores deve ser escrito diretamente no corpo da resposta.
    - Uso de `@RequestMapping` no nível da classe para definir o caminho base e o tipo de conteúdo (produzido como JSON) para as respostas dos métodos manipuladores.

**Aplicação Prática:**

- O trecho exemplifica a implementação de controladores RESTful na construção de APIs com Spring MVC, destacando como diferentes anotações são usadas para mapear as operações CRUD (criar, ler, atualizar, deletar) aos métodos HTTP correspondentes. A criação de um endpoint para buscar tacos recentes serve como caso prático para ilustrar como dados podem ser recuperados e enviados ao cliente em formato JSON, facilitando a interação com aplicações clientes, como interfaces de usuário baseadas em JavaScript.

**Implicações para o Desenvolvimento:**

- A estrutura e as anotações providas pelo Spring MVC permitem uma abordagem declarativa para a criação de APIs RESTful, simplificando o desenvolvimento de back-ends para aplicações modernas baseadas na web e em dispositivos móveis.
- A habilidade de especificar o tipo de conteúdo através do atributo `produces` e de permitir requisições cross-origin com `@CrossOrigin` aumenta a flexibilidade e a interoperabilidade dos serviços RESTful com diferentes clientes e origens.

**Palavras-Chave:** Spring MVC, RESTful API, JSON, CRUD, @RestController, HTTP methods.

---

Esta nota Zettel resume os conceitos fundamentais sobre a criação de controladores RESTful usando Spring MVC, enfatizando a diferença entre responder a requisições HTTP com HTML ou formatos de dados como JSON/XML, e detalha a utilização de anotações específicas do Spring para mapear essas operações.
```
@RestController
@RequestMapping(path = "/api/tacos", produces = "application/json")
public class TacoController {

    @GetMapping(params = "recent")
    public Iterable<Taco> recentTacos() {
        // ... (implementação para buscar tacos recentes)
    }
}
```
*
## References
*
