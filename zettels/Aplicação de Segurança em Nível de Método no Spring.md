230320242245
Status: #idea #Fleeting 
Tags: #Programação  #web  #Spring 
# Aplicação de Segurança em Nível de Método no Spring
**Palavras-chave**: Segurança em Nível de Método, Spring Security, @PreAuthorize, @PostAuthorize, AccessDeniedException

## Contexto

Embora seja comum pensar em segurança no nível das requisições web, nem sempre é o melhor local para aplicar restrições de segurança. Em muitos casos, é mais eficaz verificar se o usuário está autenticado e possui autorização adequada no momento em que a ação segura será executada.

## Ideia Principal

A anotação `@PreAuthorize` do Spring Security permite aplicar segurança em nível de método, controlando o acesso a métodos específicos com base na avaliação de uma expressão na Linguagem de Expressão de Segurança (SpEL). Isso é útil para restringir o acesso a métodos que devem ser executados apenas sob certas condições de segurança, como ter uma função específica.
```
@PreAuthorize("hasRole('ADMIN')")
public void deleteAllOrders() {
    orderRepository.deleteAll();
}
```
Neste exemplo, somente usuários com a função `ADMIN` podem executar o método `deleteAllOrders`, evitando a exclusão não autorizada de pedidos.

## Vantagens

- **Controle Granular**: A segurança em nível de método oferece controle preciso sobre quem pode executar métodos específicos, melhorando a postura de segurança da aplicação.
- **Lógica de Segurança Centralizada**: Ao embutir restrições de segurança diretamente nos métodos de serviço, os desenvolvedores podem centralizar a lógica de segurança, facilitando a gestão e auditoria.
- **Simplicidade**: O uso de anotações como `@PreAuthorize` simplifica a aplicação de regras de segurança, tornando o código mais legível e fácil de manter.

## Considerações

- **Habilitação da Segurança Global em Nível de Método**: Para usar `@PreAuthorize`, a segurança global em nível de método deve ser habilitada na classe de configuração de segurança usando a anotação `@EnableGlobalMethodSecurity`.
- **Tratamento de Exceções**: Se o acesso for negado, uma `AccessDeniedException` será lançada. Essa exceção pode ser tratada globalmente ou localmente para implementar um comportamento personalizado ou mecanismos de feedback ao usuário.

## Anotações Complementares

- **@PostAuthorize**: Similar a `@PreAuthorize`, mas avalia a expressão de segurança após a execução do método. Útil para condições que dependem do resultado do método.

## Nota de Implementação

A habilitação da segurança em nível de método requer uma consideração cuidadosa da estratégia geral de segurança da aplicação, garantindo que as anotações de segurança sejam aplicadas consistentemente e revisadas regularmente como parte do processo de desenvolvimento.
*
## References
[[Configuração de Autenticação e Segurança em Aplicações Spring]]
[[UserDetails em spring]]
[[Anotação @PostAuthorize no Spring Security]]
*
