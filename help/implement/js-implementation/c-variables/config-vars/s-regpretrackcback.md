---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.registerPreTrackCallback e s.registerPostTrackCallback

Essas funções têm como parâmetros: a chamada de retorno (como função) e os parâmetros para esta função. Por exemplo:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

A chamada de retorno é disparada quando o `requestUrl` e qualquer parâmetro passado quando a chamada de retorno é registrada. Isso ocorre antes ou depois da chamada de rastreamento, dependendo de qual método é usado para registrar a chamada de retorno.

A ordem a qual essas chamadas de retorno são feitas não é garantida. As chamadas de retorno registradas na pré-função são disparadas após a criação do URL de rastreamento final. As chamadas de retorno posteriores são feitas após uma chamada de rastreamento bem-sucedida (se a chamada de rastreamento falhar, essas funções não são usadas). Qualquer chamada de retorno registrada com o `registerPreTrackCallback` não afeta a chamada de rastreamento. Além disso, o uso dos métodos de rastreamento em qualquer chamada de retorno registrada não é recomendado e pode gerar uma repetição infinita.
