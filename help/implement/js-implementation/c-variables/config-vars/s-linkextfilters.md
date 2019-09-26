---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkExternalFilters

Se seu site contiver muitos links para sites externos e você não quiser rastrear todos os links de saída, use o para criar relatórios sobre um subconjunto específico de links de saída.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Caminhos &gt; Entradas e saídas &gt; Links de saída | "" |

A variável  variable is an optional variable used in conjunction with  to determine whether a link is an exit link. *`linkExternalFilters`**`linkInternalFilters`* Um link de saída é definido como qualquer link que leva um visitante para fora do site. Se a janela de destino de um link de saída for um pop-up ou a janela existente, isso não afeta o fato de o link aparecer ou não no relatório de links de saída. Os links de saída são rastreados somente se *`trackExternalLinks`* is set to 'true.' Os filtros em *`linkExternalFilters`* e *`linkInternalFilters`* não distinguem maiúsculas de minúsculas.

>[!NOTE]
>
>Se não quiser usar *`linkExternalFilters`*, exclua-o ou defina-o como "".

Os filtros listam no domínio *`linkExternalFilters`* e *`linkInternalFilters`* se aplicam ao caminho de qualquer link por padrão. If  is set to 'true,' the filters apply to the entire URL (domain, path, and query string). *`linkLeaveQueryString`* Esses filtros são sempre aplicados ao caminho absoluto do URL, mesmo se um caminho relativo for usado como valor href.

A maioria das empresas descobre que *`linkInternalFilters`* oferece a elas controle suficiente sobre links de saída de que elas não precisam *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

O exemplo a seguir ilustra como essa variável é usada. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

## Sintaxe e valores possíveis

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. Não são permitidos espaços.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Qualquer parte de uma URL pode ser incluída em *`linkExternalFilters`*, separados por vírgulas.

## Exemplos

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

## Configurações

Nenhuma

## Armadilhas, dúvidas e dicas

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. Não use essa variável no lugar de *`linkInternalFilters`* para forçar links internos a se tornarem links de saída.

* Se *`linkExternalFilters`* deve ser aplicado à string de consulta de um link, verifique se *`linkLeaveQueryString`* está definido como 'true'. See [linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.
