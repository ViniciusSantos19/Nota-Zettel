240320242207
Status: #idea #Fleeting 
Tags: #Programação #Spring #web
# Declarando Metadados de Propriedades de Configuração no Spring Boot
**Contexto**: No Spring Boot, as propriedades de configuração personalizadas permitem que os desenvolvedores externalizem configurações que podem ser alteradas sem modificar o código. No entanto, os IDEs podem não reconhecer essas propriedades personalizadas por padrão, gerando avisos sobre propriedades desconhecidas. Adicionar metadados para essas propriedades pode melhorar a experiência de desenvolvimento, fornecendo documentação e recursos de auto-completar diretamente no ambiente do IDE.

**Objetivo**: Eliminar avisos do IDE relacionados a propriedades de configuração personalizadas e fornecer aos desenvolvedores informações úteis sobre essas propriedades diretamente dentro do ambiente do IDE.

**Procedimento**:

1. **Localização dos Metadados**: Crie um arquivo JSON chamado `additional-spring-configuration-metadata.json` dentro do diretório `src/main/resources/META-INF`. Esse arquivo conterá os metadados para as suas propriedades de configuração personalizadas.
    
2. **Estrutura do Conteúdo dos Metadados**:
    
    - O objeto JSON de metadados contém um array `properties`.
    - Cada item no array representa uma única propriedade de configuração, incluindo atributos como `name`, `type` e `description`.
3. **Exemplo de Entrada de Metadados**:
    ```
    {
  "properties": [{
    "name": "taco.orders.page-size",
    "type": "java.lang.Integer",
    "description": "Define o número máximo de pedidos para exibir em uma lista."
	  }]
	}
    ```
    
    - **Nome**: Reflete o caminho completo da propriedade, usando hifens (-) em vez de camelCase.
    - **Tipo**: Especifica o tipo de dados da propriedade, como `java.lang.Integer`.
    - **Descrição**: Fornece uma descrição clara e concisa do que a propriedade faz ou controla.
2. **Suporte Aprimorado no IDE**:
    
    - **Documentação**: Passar o mouse sobre uma propriedade de configuração no IDE exibirá a descrição fornecida nos metadados.
    - **Auto-completar**: Ao editar o arquivo `application.yml` ou `application.properties`, o IDE oferecerá sugestões de auto-completar com base nos metadados.
3. **Benefícios**:
    
    - **Experiência do Desenvolvedor**: Melhora a clareza e a facilidade de uso para desenvolvedores que trabalham com propriedades de configuração personalizadas.
    - **Documentação**: Serve como documentação dentro do IDE para as propriedades, reduzindo a necessidade de consultar documentação externa.
    - **Consistência**: Ajuda a manter a consistência no uso das propriedades em diferentes partes do aplicativo e entre diferentes desenvolvedores.

**Conclusão**: Ao declarar metadados para propriedades de configuração personalizadas, os desenvolvedores podem reduzir os avisos do IDE e melhorar a experiência geral de desenvolvimento. Esta prática suporta uma melhor documentação, validação e usabilidade das propriedades de configuração dentro de aplicações Spring Boot.
*
## References
[[Criação e Uso de Propriedades de Configuração Customizadas no Spring Boot]]
*
