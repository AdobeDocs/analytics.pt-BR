---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.linkExternalFilters

Se seu site contiver muitos links para sites externos e você não quiser rastrear todos os links de saída, use o para criar relatórios sobre um subconjunto específico de links de saída.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | N/D | Caminhos &gt; Entradas e saídas &gt; Links de saída | "" |

A *`linkExternalFilters`* é uma variável opcional usada em conjunto com *`linkInternalFilters`* para determinar se um link é de saída. Um link de saída é definido como qualquer link que leva um visitante para fora do site. Se a janela de destino de um link de saída for um pop-up ou a janela existente, isso não afeta o fato de o link aparecer ou não no relatório de links de saída. Os links de saída são rastreados somente se  *`trackExternalLinks`* foi definida como 'true'. Os filtros em *`linkExternalFilters`* e *`linkInternalFilters`* não fazem distinção entre maiúsculas e minúsculas.

> [!NOTE] Se não quiser usar *`linkExternalFilters`*, exclua ou defina como "".

As listas de filtros *`linkExternalFilters`* e *`linkInternalFilters`* se aplicam ao domínio e ao caminho de qualquer link por padrão. Se *`linkLeaveQueryString`* estiver definido como 'true', os filtros serão aplicados a todo o URL (domínio, caminho e sequência de consulta). Esses filtros são sempre aplicados ao caminho absoluto do URL, mesmo se um caminho relativo for usado como valor href.

A maioria das empresas descobre que  *`linkInternalFilters`* oferece a elas controle suficiente sobre links de saída de que elas não precisam *`linkExternalFilters`*. O uso de *`linkExternalFilters`* simplesmente reduz a probabilidade de um link de saída ser considerado externo. Se *`linkExternalFilters`* tiver um valor, então um link será considerado externo somente se não corresponder a *`linkInternalFilters`* e corresponder a *`linkExternalFilters`*.

O exemplo a seguir ilustra como essa variável é usada. Neste exemplo, o URL da página é `https://www.mysite.com/index.html`.

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

*`linkExternalFilters`*&#x200B;é uma lista de caracteres ASCII separada por vírgulas. Não são permitidos espaços.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Qualquer parte de uma URL pode ser incluída em  *`linkExternalFilters`*, separados por vírgulas.

## Exemplos

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

* O uso de *`linkExternalFilters`* pode resultar em menos links de saída em seu site. Não use essa variável no lugar de *`linkInternalFilters`* para forçar links internos a se tornarem links de saída.

* Se *`linkExternalFilters`* deve ser aplicado à sequência de consulta de um link, verifique se *`linkLeaveQueryString`* está definido como 'true'. Consulte [linkLeaveQueryString](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) antes de configurar como `"true"`.

* Para desativar o rastreamento de link de saída, configure *`trackExternalLinks`* como `"false"`.
