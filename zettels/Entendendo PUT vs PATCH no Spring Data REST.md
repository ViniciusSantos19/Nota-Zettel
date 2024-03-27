260320242210
Status: #idea #Fleeting 
Tags:  #Programação  #web #Spring 
# Entendendo PUT vs PATCH no Spring Data REST
Nos serviços RESTful, a atualização de recursos no servidor pode ser realizada utilizando métodos HTTP, especificamente PUT e PATCH. Embora esses métodos pareçam similares, servem a propósitos distintos na manipulação de recursos. O Spring Data REST fornece as anotações `@PutMapping` e `@PatchMapping` para tratar esses métodos respectivamente, cada um adaptado a diferentes estratégias de atualização.

#### PUT para Substituição Completa do Recurso

A anotação `@PutMapping` é usada para tratar requisições HTTP PUT. Semanticamente, uma requisição PUT substitui o recurso inteiro pelos dados fornecidos. Isso implica que o cliente deve enviar uma representação completa do recurso, mesmo que apenas um subconjunto de propriedades seja alterado. Propriedades ausentes na requisição são tipicamente interpretadas como valores nulos, o que pode levar à perda de dados não intencionada se não for manuseado com cuidado.

Por exemplo, atualizar o endereço de um pedido pode ser feito da seguinte forma:
```
@PutMapping(path="/{orderId}", consumes="application/json")
public TacoOrder putOrder(@PathVariable("orderId") Long orderId, @RequestBody TacoOrder order) {
    order.setId(orderId);
    return repo.save(order);
}
```
Este método substitui o recurso `TacoOrder` inteiro com os novos dados fornecidos no corpo da requisição.

#### PATCH para Atualizações Parciais do Recurso

Por outro lado, a anotação `@PatchMapping` lida com requisições HTTP PATCH, projetadas para atualizações parciais de um recurso. Este método permite que os clientes enviem apenas as alterações que desejam aplicar ao recurso, sem necessidade de fornecer uma representação completa.

Uma operação PATCH pode parecer assim:
```
@PatchMapping(path="/{orderId}", consumes="application/json")
public TacoOrder patchOrder(@PathVariable("orderId") Long orderId, @RequestBody TacoOrder patch) {
    TacoOrder order = repo.findById(orderId).get();
    if (patch.getDeliveryName() != null) { order.setDeliveryName(patch.getDeliveryName()); }
    // Verificações e atualizações adicionais para outros campos
    return repo.save(order);
}
```
Este método atualiza apenas os campos não nulos do objeto `TacoOrder`, preservando os dados originais para quaisquer campos não explicitamente mencionados na requisição de patch.

#### Diferenças Chave e Considerações Práticas

- **Uso Pretendido**: PUT é destinado a substituições completas, PATCH para atualizações parciais.
- **Manuseio de Dados**: Com PUT, campos ausentes são frequentemente definidos como nulos. PATCH atualiza seletivamente campos, deixando campos não especificados intocados.
- **Complexidade**: Implementações de PATCH podem ser mais complexas, pois precisam de lógica para identificar e aplicar apenas as alterações especificadas na requisição.

#### Limitações e Soluções

Enquanto PATCH oferece flexibilidade para atualizações parciais, também introduz desafios, como indicar que um campo deve ser explicitamente definido como nulo ou como gerenciar coleções de forma eficiente. Esses desafios frequentemente requerem uma abordagem mais sofisticada, potencialmente envolvendo formatos ou operações de patch personalizados.

Tanto `@PutMapping` quanto `@PatchMapping` exigem o identificador do recurso no caminho da requisição, garantindo que o recurso correto seja alvo de atualizações. A escolha entre PUT e PATCH no design da API depende dos requisitos específicos para a manipulação de recursos, equilibrando entre a facilidade de uso, eficiência de rede e a granularidade de controle sobre o estado do recurso.
*
## References
[[Manipulação de Dados em REST APIs com Spring MVC]]
[[Controladores RESTful em Spring MVC]]
*
