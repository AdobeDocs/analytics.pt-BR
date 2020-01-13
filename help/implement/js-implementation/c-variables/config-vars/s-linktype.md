---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 21f278017472ae39c6066ca7694a5cdbbfde41f3

---


# s.linkType

Contém o tipo de link determinado automaticamente, se houver. Pode ser definido como um dos seguintes:

    * `d` (download)
    * `e` (saída)
    * `o` (personalizado/outro)

Este é o parâmetro `pe` na solicitação de imagem. Se definido com [`linkURL`](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkURL.html) ou [`linkName`](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html), uma chamada de servidor é enviada como um link de download, personalizado ou de saída.

*Observação: a variável[`pageName`](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.html)não pode ser definida para um download de arquivo, link de saída, ou link personalizado, porque nenhum dos tipos de link é uma exibição de página e não tem um nome de página associado.*


**Exemplo**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```
