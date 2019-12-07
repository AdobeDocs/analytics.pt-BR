---
description: O arquivo .js pode ser configurado para selecionar automaticamente uma ID de conjunto de relatórios.
keywords: Analytics Implementation
title: IDs de conjunto de relatórios - Contas dinâmicas
topic: Developer and implementation
uuid: 763a9741-309d-4795-8819-6543866047d5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# IDs de conjunto de relatórios - Contas dinâmicas

O arquivo .js pode ser configurado para selecionar automaticamente uma ID de conjunto de relatórios. O arquivo .js envia automaticamente a solicitação de imagem para o conjunto de relatórios com base no URL. Por exemplo, se o URL for `www.mysite.com`, a solicitação de imagem é enviada automaticamente para o conjunto de relatórios A. Se o URL for `www.mysite1.com`, a solicitação de imagem é enviada automaticamente para o conjunto de relatórios B.

As strings podem ser encontradas em:

* Host/domínio (configuração padrão)
* Caminho
* String de consulta
* Host/domínio e caminho
* Caminho e string de consulta
* URL completo

Para obter mais informações sobre a configuração do [!DNL Analytics] para selecionar automaticamente uma [!UICONTROL  ID do conjunto de relatórios], entre em contato com o suporte da Adobe ao vivo.

## Definição do segmento do URL para correspondência {#section_8099162F75F641CFBE46FD814450EF36}

Dado o exemplo de URL a seguir, as partes do URL são mostradas abaixo, juntamente com a variável `s.dynamicAccountMatch` que deve ser definida. (O padrão se `s.dynamicAccountMatch` não for definida é pesquisar apenas o Host/Nome de domínio).
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

O código verifica primeiro para determinar se existe `qa.client.com` no Host/Nome de domínio. Se existir, o conjunto de relatórios `devreportsuite1` é selecionado e a correspondência é interrompida. Separe várias regras com pontos-e-vírgulas.

## Conjunto de relatórios padrão {#section_0360D724929348B0B211708B5BA15647}

A variável `s_account` pode ser definida primeiro e atua como valor padrão, caso não seja possível encontrar uma das strings especificadas. Abaixo há um exemplo:

```javascript
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

No caso acima, se o host/nome de domínio não contiver `qa.client.com` ou `client.com`, o conjunto de relatórios *defaultreportsuiteid* será usado.
