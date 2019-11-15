---
description: O sinalizador de anulação pode ser configurado dentro de doPlugins, fazendo com que a chamada de rastreamento atual não seja enviada.
keywords: Analytics Implementation
solution: Analytics
title: s.abort flag
topic: Developer and implementation
uuid: 0c6ec8c7-d136-4851-8cb6-6cb1b7f6f0dc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.abort flag

O sinalizador de anulação pode ser configurado dentro de doPlugins, fazendo com que a chamada de rastreamento atual não seja enviada.

O sinalizador abort é redefinido em cada chamada de rastreamento, portanto, se uma chamada de rastreamento subsequente também precisar ser abortada, o sinalizador precisará ser configurado novamente dentro de doPlugins.

```js
s.doPlugins = function(s) { 
     s.campaign = s.getQueryParam("cid"); 
     if ((!s.campaign) && (!s.events)) { 
          s.abort = true; 
     } 
};
```

Isso permite que você centralize a lógica usada para identificar a atividade que você não deseja rastrear, como links personalizados ou links externos na exibição de anúncios.
