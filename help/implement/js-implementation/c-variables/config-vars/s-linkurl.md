---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 1773e84809e04b3be25c77bf1fb8ad8317b7f8c0

---


# s-linkURL

O URL do link, que atua como o nome se um `linkName` não existir. Pode ser definido como qualquer string de URL. Este é o parâmetro `pev1` na solicitação de imagem.


Se definido como [`linkType`](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html), uma solicitação de imagem será enviada como link de download, personalizado ou de saída.


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
