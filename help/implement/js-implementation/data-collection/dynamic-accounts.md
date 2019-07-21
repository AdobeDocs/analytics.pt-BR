---
description: O arquivo .js pode ser configurado para selecionar automaticamente uma ID de conjunto de relatórios.
keywords: Implementação do Analytics
seo-description: O arquivo .js pode ser configurado para selecionar automaticamente uma ID de conjunto de relatórios.
seo-title: IDs do conjunto de relatórios - contas dinâmicas
solution: Analytics
title: IDs do conjunto de relatórios - contas dinâmicas
topic: Desenvolvedor e implementação
uuid: 763 a 9741-309 d -4795-8819-6543866047 d 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# IDs do conjunto de relatórios - contas dinâmicas

O arquivo .js pode ser configurado para selecionar automaticamente uma ID de conjunto de relatórios. O arquivo .js envia automaticamente a solicitação de imagem para o conjunto de relatórios com base no URL. Por exemplo, se o URL for `www.mysite.com`, a solicitação de imagem é enviada automaticamente para o conjunto de relatórios A. Se o URL for `www.mysite1.com`, a solicitação de imagem é enviada automaticamente para o conjunto de relatórios B.

As strings podem ser encontradas em:

* Host/domínio (configuração padrão)
* Caminho
* String de consulta
* Host/domínio e caminho
* Caminho e string de consulta
* URL completo

Para obter mais informações sobre a configuração do [!DNL Analytics]   para selecionar automaticamente uma [!UICONTROL  ID do conjunto de relatórios], entre em contato com o suporte da Adobe ao vivo.

## Definição do segmento do URL para correspondência {#section_8099162F75F641CFBE46FD814450EF36}

Dado o exemplo de URL a seguir, as partes do URL são mostradas abaixo, juntamente com a variável `s.dynamicAccountMatch` que deve ser definida (O padrão se `s.dynamicAccountMatch` não for definida é pesquisar apenas o Host/Nome de domínio).
Amostra do URL: `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321`

| Parte | Exemplo (do acima) |
|---|---|
| Host/Nome de domínio | `www.client.com` |
| Caminho | `directory1/directory2/filename.html` |
| String de consulta | `param1=1234&param2=4321` |
| Host/domínio e caminho | `www.client.com/directory1/directory2/filename.html` |
| Caminho e string de consulta | `directory1/directory2/filename.html?param1=1234&param2=4321` |
| URL | `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321` |
| Parte | `s.dynamicAccountmatch` |
| Host/Nome de domínio | Indefinido |
| Caminho | `window.location.pathname` |
| String de consulta | `(window.location.search?window.location.search:"?")` |
| Host/domínio e caminho | `window.location.host+window.location.pathname` |
| Caminho e string de consulta | `window.location.pathname+(window.location.search?window.location.search:"?")` |
| URL | `window.location.href` |

Considere o exemplo a seguir:

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite2=clientdirectory;reportsuite1=client.com"`
* `s.dynamicAccountMatch=window.location.host+window.location.pathname`

## Várias Regras {#section_163FED1C1FA74C48BCB78B0D67EF36AE}

Se várias regras estiver selecionado (consulte exemplo acima), as regras serão executadas da esquerda para a direita. As regras são interrompidas assim que ocorre uma correspondência, como mostrado abaixo (com o conjunto de regras determinado).

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com"`

The code first checks to determine if `qa.client.com` exists within the Host/Domain Name. If so, the report suite `devreportsuite1` is selected, and the match stops. Separe várias regras com pontos-e-vírgulas.

## Conjunto de relatórios padrão {#section_0360D724929348B0B211708B5BA15647}

The `s_account` variable can be set first, and acts as a default value in case any of the specified strings cannot be found. Abaixo há um exemplo:

```javascript
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

In the case above, if the host/domain name did not contain either `qa.client.com` or `client.com`, the report suite *defaultreportsuiteid* would be used.
