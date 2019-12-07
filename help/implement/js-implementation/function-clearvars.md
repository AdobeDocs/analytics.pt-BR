---
description: Apaga os valores a seguir do objeto da instância. Essa função remove os elementos (define-os como "indefinidos").
keywords: Analytics Implementation
title: A função s.clearVars()
topic: Developer and implementation
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

