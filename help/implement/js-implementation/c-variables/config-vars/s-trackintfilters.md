---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.linkInternalFilters

A variável é usada para determinar quais links de seu site são de saída.

Trata-se de uma lista de filtros separada por vírgulas que representa os links que são parte do site.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Caminhos &gt; Entradas e saídas &gt; Links de saída |  |

>[!NOTE]
>
>Anteriormente, sugerimos definir linkInternalFilters como javascript:. No entanto, isso fez com que todos os domínios fossem considerados externos, incluindo o domínio atual no qual a tag reside. Se você quiser que vários domínios sejam considerados internos, poderá adicioná-los, conforme mostrado nos exemplos abaixo.

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. Se a janela de destino de um link de saída for um pop-up ou a janela existente, isso não afeta o fato de o link aparecer ou não no relatório de links de saída. Os links de saída só são acompanhados se *`trackExternalLinks`* está definida como `"true"`. (Consulte [Rastreamento de links](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) na documentação do Dynamic Tag Management para obter informações sobre como o DTM processa os links de saída.) Os filtros não *`linkInternalFilters`* fazem distinção entre maiúsculas e minúsculas.

A lista de filtros em *`linkInternalFilters`* se aplica ao domínio e ao caminho de qualquer link por padrão. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). Esses filtros são sempre aplicados ao caminho absoluto do URL, mesmo se um caminho relativo for usado como o valor href.

Tenha cuidado para que todos os domínios de seu site (e quaisquer parceiros que estejam usando seu arquivo JavaScript) estejam incluídos na *`linkInternalFilters`*. Se nem todos os domínios foram incluídos na lista, todos os links de e para esses domínios serão considerados como links de saída, aumentando as chamadas para servidor enviadas. Se desejar que vários domínios ou empresas usem um único [!DNL AppMeasurement] para o arquivo JavaScript, você pode considerar preencher *`linkInternalFilters`* a página, substituindo o valor especificado no arquivo JavaScript. Se você tiver domínios vanity que redirecionam imediatamente para o seu domínio principal, esses domínios vanity não precisam ser incluídos na lista.

O exemplo a seguir ilustra como essa variável é usada. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

## Sintaxe e valores possíveis

The *`linkInternalFilters`* variable is a comma-separated list of ASCII characters. Não são permitidos espaços.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## Exemplos

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## Configurações

Nenhuma

## Armadilhas, dúvidas e dicas

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* Verifique periodicamente o relatório [!UICONTROL Caminhos] &gt; [!UICONTROL Entradas e saídas] &gt; [!UICONTROL Saída] para verificar se nenhuma das entradas desse relatório está incorreta.

* Periodicamente, examine os contratos de parceiros para determinar se eles contêm restrições ao rastreamento de links. Por exemplo, você pode ser proibido de rastrear links exibidos nos anúncios de exibição do parceiro. Filtre os links do parceiro adicionando seu domínio a *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```
