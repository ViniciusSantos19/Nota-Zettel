230320242306
Status: #idea #Fleeting 
Tags: #Spring #web 
# Identificação do Usuário Autenticado no Spring Security
## Contexto

Em uma aplicação Spring Security, é comum precisar identificar quem é o usuário autenticado para personalizar a experiência do usuário e associar dados específicos a ele.

## Ideia Principal

Existem várias maneiras de identificar o usuário autenticado no Spring Security. Isso inclui injetar objetos `java.security.Principal` ou `Authentication`, acessar o contexto de segurança usando `SecurityContextHolder`, ou mesmo aceitar diretamente um objeto `User` anotado com `@AuthenticationPrincipal` em métodos de controlador.

## Exemplo
```
@PostMapping
public String processOrder(@Valid TacoOrder order, Errors errors,
                          SessionStatus sessionStatus,
                          @AuthenticationPrincipal User user) {
    if (errors.hasErrors()) {
        return "orderForm";
    }
    order.setUser(user);
    orderRepo.save(order);
    sessionStatus.setComplete();
    return "redirect:/";
}
```
## Vantagens

- **Clareza e Conveniência**: Anotar um parâmetro de método com `@AuthenticationPrincipal` elimina a necessidade de fazer cast ou acessar manualmente o contexto de segurança, tornando o código mais limpo e legível.
- **Segurança de Nível Inferior**: O acesso ao `Authentication` diretamente do `SecurityContextHolder` permite identificar o usuário autenticado em qualquer lugar da aplicação, não apenas em métodos de controlador.

## Considerações

- **Flexibilidade versus Segurança**: Embora seja conveniente, usar `@AuthenticationPrincipal` pode não ser a opção mais segura em todos os casos, especialmente se o objeto `User` contiver informações sensíveis.
- **Custo de Desempenho**: Dependendo da frequência de acesso ao contexto de segurança, pode haver um leve custo de desempenho ao acessar essas informações repetidamente.

## Aplicabilidade

A escolha entre as diferentes abordagens para identificar o usuário autenticado depende das necessidades específicas da aplicação e da preferência do desenvolvedor. O uso de `@AuthenticationPrincipal` é geralmente recomendado para métodos de controlador, enquanto o acesso direto ao contexto de segurança pode ser mais adequado para outros componentes da aplicação.
*
## References
[[Anotação @PostAuthorize no Spring Security]]
[[Anotação @PostAuthorize no Spring Security]]
[[Aplicação de Segurança em Nível de Método no Spring]]
*
