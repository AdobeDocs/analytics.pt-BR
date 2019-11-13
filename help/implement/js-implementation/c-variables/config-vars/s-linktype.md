---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.linkType

Contém o tipo de link determinado automaticamente, se houver. Pode ser definido como um dos seguintes:

    * "d" (download)
    * "e" (saída)
    * "o" (personalizado/outro)

Este é o parâmetro `pe` na solicitação de imagem. Se definido com `linkURL` ou `linkName`, uma chamada de servidor é enviada como um link de download, personalizado ou de saída.

*Observação: A variável[`pageName`](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.html)não pode ser definida para um download de arquivo, link de saída ou link personalizado, pois cada tipo de link não é uma exibição de página e não tem um nome de página associado.*


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
