240320242148
Status: #idea #Fleeting 
Tags:  #Programação #Spring #web 
# Criação e Uso de Propriedades de Configuração Customizadas no Spring Boot
- **Contexto e Utilidade:** As propriedades de configuração no Spring Boot são essenciais para personalizar o comportamento de beans, baseando-se na abstração do ambiente do Spring. Essas propriedades são definidas em arquivos de configuração ou variáveis de ambiente e injetadas em beans específicos para ajustar sua configuração de forma flexível e dinâmica.
    
- **@ConfigurationProperties:** A anotação `@ConfigurationProperties` é usada para designar beans que podem receber propriedades de configuração do ambiente do Spring. Ao aplicar esta anotação a um bean, indica-se que suas propriedades podem ser configuradas através de propriedades do ambiente, utilizando um prefixo específico definido no atributo `prefix`.
    
- **Exemplo Prático:** No controle de pedidos (`OrderController`) de uma aplicação de pedidos de tacos, a necessidade de limitar o número de pedidos exibidos na UI a um número específico de registros recentes. Originalmente, o método `ordersForUser()` foi modificado para solicitar apenas os 20 pedidos mais recentes usando `PageRequest`. Contudo, a quantidade de pedidos a ser exibida estava hardcoded, levando à necessidade de uma abordagem mais flexível.
    
- **Implementação de Propriedades Customizadas:** Para tornar o tamanho da página configurável, um novo campo `pageSize` é adicionado ao `OrderController`, e a classe é anotada com `@ConfigurationProperties(prefix="taco.orders")`. Isso permite que o tamanho da página seja configurado externamente via propriedades de configuração, como `taco.orders.pageSize`, eliminando a necessidade de hardcoding e permitindo ajustes dinâmicos sem recompilação.
    
- **Extração para Classe de Propriedades:** Para uma melhor organização e reuso das propriedades de configuração, é recomendável extrair propriedades específicas para uma classe dedicada de detentores de propriedades de configuração. Isso é realizado criando uma nova classe, por exemplo, `OrderProps`, e movendo a propriedade `pageSize` para ela. Essa classe é então anotada com `@ConfigurationProperties` e `@Component`, tornando-a um bean gerenciado pelo Spring e centralizando as propriedades de configuração relacionadas a pedidos.
    
- **Injeção de Propriedades e Reutilização:** A classe de propriedades de configuração (`OrderProps`) pode então ser injetada em `OrderController` ou qualquer outro bean que necessite dessas propriedades, promovendo a reutilização e mantendo a separação de preocupações. Além disso, facilita a manutenção, pois qualquer mudança nas propriedades de configuração precisa ser aplicada em um único local.
    
- **Validação de Propriedades:** A classe `OrderProps` pode ser anotada com `@Validated` para habilitar a validação de propriedades de configuração, usando anotações como `@Min` e `@Max`, garantindo que os valores configurados estejam dentro de limites aceitáveis. Isso centraliza a validação de configurações relacionadas a pedidos, simplificando a gestão e manutenção de regras de validação.
    

**Conclusão:** A utilização de `@ConfigurationProperties` no Spring Boot facilita a criação de propriedades de configuração customizadas, permitindo uma configuração flexível e dinâmica de beans, além de promover boas práticas como a separação de preocupações e a reutilização de código.

### Exemplo
```
package tacos.web;
import javax.validation.constraints.Max;
import javax.validation.constraints.Min;
import org.springframework.boot.context.properties.
ConfigurationProperties;
import org.springframework.stereotype.Component;
import org.springframework.validation.annotation.Validated;
import lombok.Data;
@Component
@ConfigurationProperties(prefix="taco.orders")
@Data
@Validated
public class OrderProps {
@Min(value=5, message="must be between 5 and 25")
@Max(value=25, message="must be between 5 and 25")
private int pageSize = 20;
}
```
```
private OrderProps props;
public OrderController(OrderRepository orderRepo,
OrderProps props) {
this.orderRepo = orderRepo;
this.props = props;
}


@GetMapping
public String ordersForUser(
@AuthenticationPrincipal User user, Model model) {
Pageable pageable = PageRequest.of(0, props.getPageSize());
model.addAttribute("orders",
orderRepo.findByUserOrderByPlacedAtDesc(user, pageable));
return "orderList";
}
```
*
## References
[[Declarando Metadados de Propriedades de Configuração no Spring Boot]]
*
