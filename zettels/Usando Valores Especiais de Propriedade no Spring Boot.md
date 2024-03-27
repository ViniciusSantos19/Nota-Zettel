240320242136
Status: #idea #Fleeting 
Tags:  #Programação #web #Spring 
# Usando Valores Especiais de Propriedade no Spring Boot
Ao definir propriedades, você não está limitado a valores literais (String e numéricos).

Você pode derivar valores de outras propriedades de configuração usando o marcador `${}`.

Por exemplo:

YAML

```
greeting:
  welcome: ${spring.application.name}  # O valor de greeting.welcome será igual ao de spring.application.name
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

É possível combinar texto com o marcador:

YAML

```
greeting:
  welcome: You are using ${spring.application.name}.
```

Use o código [com cuidado](https://gemini.google.com/faq#coding).

Isso permite que seus beans personalizados também se beneficiem das propriedades de configuração do Spring Boot.
*
## References
*
