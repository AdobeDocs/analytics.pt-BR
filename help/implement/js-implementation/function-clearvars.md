---
description: Apaga os valores a seguir do objeto da instância. Essa função remove os elementos (define-os como "indefinidos").
keywords: Implementação do Analytics
seo-description: Apaga os valores a seguir do objeto da instância. Essa função remove os elementos (define-os como "indefinidos").
seo-title: A função s.clearVars()
solution: Analytics
title: A função s.clearVars()
topic: Desenvolvedor e implementação
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

---


# A função s.clearVars()

Apaga os valores a seguir do objeto da instância. Essa função remove os elementos (define-os como "indefinidos").

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

Por exemplo:

```js
s.clearVars()
```

>[!NOTE]
>
>`clearVars()` está incluso no [AppMeasurement para JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md), mas não está disponível no código H e nas versões anteriores.

