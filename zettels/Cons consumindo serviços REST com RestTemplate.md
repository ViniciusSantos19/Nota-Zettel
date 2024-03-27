260320242237
Status: #idea #Fleeting 
Tags:  #Programação #web #Spring 
# Cons consumindo serviços REST com RestTemplate
**Ideias principais:**

- Spring fornece RestTemplate para simplificar a interação com serviços REST.
- RestTemplate evita a escrita de código boilerplate para criação de requisições HTTP.
- RestTemplate oferece métodos sobrecarregados para os principais verbos HTTP (GET, PUT, POST, DELETE).

**Exemplos de código:**

Criando uma instância de RestTemplate:

Java

```
RestTemplate rest = new RestTemplate();
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

Declarando RestTemplate como bean:

Java

```
@Bean
public RestTemplate restTemplate() {
  return new RestTemplate();
}
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

**Métodos RestTemplate:**

- `getForObject(String url, Class<T> responseType)`: Envia uma requisição GET e retorna o objeto mapeado da resposta.
- `getForEntity(String url, Class<T> responseType)`: Envia uma requisição GET e retorna um ResponseEntity contendo o objeto mapeado da resposta.

**Observações:**

- RestTemplate possui outros métodos para GET (e demais verbos HTTP) que aceitam URL com parâmetros como argumento.
- É importante conhecer os 12 métodos principais de RestTemplate para escrever clientes consumidores de serviços REST.
*
## References
[[Habilitando serviços baseados em dados com Spring Data REST]]
*
