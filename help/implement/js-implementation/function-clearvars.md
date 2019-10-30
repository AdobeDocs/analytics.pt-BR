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
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

> [!NOTE] `clearVars()` está incluso no [AppMeasurement para JavaScript](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8), mas não está disponível no código H e nas versões anteriores.

