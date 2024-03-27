260320242245
Status: #idea  #Fleeting 
Tags: #Programação #web #Spring 
# Consumindo serviços REST com RestTemplate - Métodos HTTP
- O RestTemplate oferece métodos sobrecarregados para realizar requisições HTTP GET, PUT, POST e DELETE.
- Cada método aceita a URL da API como String podendo conter parâmetros como `{id}`.
- Os parâmetros da URL podem ser passados como lista de argumentos variáveis ou através de um Map.
- Também é possível utilizar URI para especificar a URL da API.

**GET**

- `getForObject(String url, Class<T> responseType, Object... urlVariables)`:
    - Executa uma requisição GET e retorna o objeto mapeado da resposta.
- `getForEntity(String url, Class<T> responseType, Object... urlVariables)`:
    - Executa uma requisição GET e retorna um ResponseEntity contendo o objeto mapeado da resposta (acesso a headers da resposta).

**Exemplo GET com lista de argumentos variáveis:**

Java

```
public Ingredient getIngredientById(String ingredientId) {
  return rest.getForObject("http://localhost:8080/ingredients/{id}", Ingredient.class, ingredientId);
}
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

**Exemplo GET com Map:**

Java

```
public Ingredient getIngredientById(String ingredientId) {
  Map<String, String> urlVariables = new HashMap<>();
  urlVariables.put("id", ingredientId);
  return rest.getForObject("http://localhost:8080/ingredients/{id}", Ingredient.class, urlVariables);
}
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

**Exemplo GET com URI:**

Java

```
public Ingredient getIngredientById(String ingredientId) {
  Map<String, String> urlVariables = new HashMap<>();
  urlVariables.put("id", ingredientId);
  URI url = UriComponentsBuilder.fromHttpUrl("http://localhost:8080/ingredients/{id}").build(urlVariables);
  return rest.getForObject(url, Ingredient.class);
}
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

**PUT**

- `put(String url, Object request, Object... urlVariables)`:
    - Envia uma requisição PUT com o objeto para atualização no corpo da requisição.

**Exemplo PUT:**

Java

```
public void updateIngredient(Ingredient ingredient) {
  rest.put("http://localhost:8080/ingredients/{id}", ingredient, ingredient.getId());
}
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

**DELETE**

- `delete(String url, Object... urlVariables)`:
    - Envia uma requisição DELETE para remover um recurso.

**Exemplo DELETE:**

Java

```
public void deleteIngredient(Ingredient ingredient) {
  rest.delete("http://localhost:8080/ingredients/{id}", ingredient.getId());
}
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

**POST**

- `postForObject(String url, Object request, Class<T> responseType, Object... urlVariables)`:
    - Envia uma requisição POST e retorna o objeto criado no corpo da resposta.
- `postForLocation(String url, Object request, Object... urlVariables)`:
    - Envia uma requisição POST e retorna a URI do recurso criado através do header Location.
- `postForEntity(String url, Object request, Class<T> responseType, Object... urlVariables)`:
    - Envia uma requisição POST e retorna um ResponseEntity contendo o objeto criado e o header Location.

**Exemplos POST:**

Java

```
// Retorna o objeto criado
public Ingredient createIngredient(Ingredient ingredient) {
  return rest.postForObject("http://localhost:8080/ingredients", ingredient, Ingredient.class);
}

// Retorna a URI do recurso criado
public java.net.URI createIngredient(Ingredient ingredient) {
  return rest.postForLocation("http://localhost:8080/ingredients", ingredient);
}

// Retorna o objeto criado e a URI do recurso 
public Ingredient createIngredient(Ingredient ingredient) {
  ResponseEntity<Ingredient> responseEntity = rest.postForEntity("http://localhost:8080/ingredients", ingredient, Ingredient.class);
  log.info("New resource created at {}", responseEntity.getHeaders().getLocation());
  return responseEntity.getBody();
}
```
*
## References
*
