---
description: O sinalizador de anulação pode ser configurado dentro de doPlugins, fazendo com que a chamada de rastreamento atual não seja enviada.
keywords: Implementação do Analytics
seo-description: O sinalizador de anulação pode ser configurado dentro de doPlugins, fazendo com que a chamada de rastreamento atual não seja enviada.
seo-title: s.abort flag
solution: Analytics
title: s.abort flag
topic: Desenvolvedor e implementação
uuid: 0 c 6 ec 8 c 7-d 136-4851-8 cb 6-6 cb 1 b 7 f 6 f 0 dc
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# s.abort flag

O sinalizador de anulação pode ser configurado dentro de doPlugins, fazendo com que a chamada de rastreamento atual não seja enviada.

O sinalizador abort é redefinido em cada chamada de rastreamento, portanto, se uma chamada de rastreamento subsequente também precisar ser abortada, o sinalizador precisará ser configurado novamente dentro de doPlugins

```js
s.doPlugins = function(s) { 
     s.campaign = s.getQueryParam("cid"); 
     if ((!s.campaign) && (!s.events)) { 
          s.abort = true; 
     } 
};
```

Isso permite que você centralize a lógica usada para identificar a atividade que você não deseja rastrear, como links personalizados ou links externos na exibição de anúncios.
