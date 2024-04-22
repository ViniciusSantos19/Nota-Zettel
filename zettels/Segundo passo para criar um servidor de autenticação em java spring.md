200420242055
Status: #idea
Tags:  #Programação #Spring #security 
# Segundo passo para criar um servidor de autenticação em java spring

Este método configura as definições do provedor de identidade OAuth2. O objeto `ProviderSettings` provavelmente será usado pela sua implementação de autenticação para interagir com o provedor e realizar a autenticação do usuário. A URI do provedor é obtida das propriedades de configuração injetadas (`authProperties`).

O segundo passo para criar nosso servidor seria configurar o gerador de tokens jwt. Para isso no tutorial que estou vendo ele adicionou esse bean na classse de configuração:

```
@Bean
    public ProviderSettings providerSettings(AuthProperties authProperties) {
        return ProviderSettings.builder()
                .issuer(authProperties.getProviderUri())
                .build();
    }
```


## AuthPropeties

A classe AuthPropeties foi criada para centralizar em apenas uma classe tudo que será necessário para configurar essa bean de ProviderSettings. Esse foi o código fornecido pelo autor do tutorial.



```
package com.algaworks.example.auth.server.security;

import org.springframework.boot.context.properties.ConfigurationProperties;
import org.springframework.stereotype.Component;
import org.springframework.validation.annotation.Validated;

import javax.validation.constraints.NotBlank;
import javax.validation.constraints.NotNull;

@Component
@Validated
@ConfigurationProperties("aw.auth")
public class AuthProperties {

    @NotBlank
    private String providerUri;

    @NotNull
    private JksProperties jks;

    public String getProviderUri() {
        return providerUri;
    }

    public void setProviderUri(String providerUri) {
        this.providerUri = providerUri;
    }

    public JksProperties getJks() {
        return jks;
    }

    public void setJks(JksProperties jks) {
        this.jks = jks;
    }

    static class JksProperties {

        @NotBlank
        private String keypass;

        @NotBlank
        private String storepass;

        @NotBlank
        private String alias;

        @NotBlank
        private String path;

        public String getKeypass() {
            return keypass;
        }

        public void setKeypass(String keypass) {
            this.keypass = keypass;
        }

        public String getStorepass() {
            return storepass;
        }

        public void setStorepass(String storepass) {
            this.storepass = storepass;
        }

        public String getAlias() {
            return alias;
        }

        public void setAlias(String alias) {
            this.alias = alias;
        }

        public String getPath() {
            return path;
        }

        public void setPath(String path) {
            this.path = path;
        }
    }
}
```
*
## References
*
