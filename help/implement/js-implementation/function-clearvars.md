---
description: Apaga os valores a seguir do objeto da instância. Essa função remove os elementos (define-os como "indefinidos").
keywords: Implementação do Analytics
seo-description: Apaga os valores a seguir do objeto da instância. Essa função remove os elementos (define-os como "indefinidos").
seo-title: A função s.clearVars()
solution: Analytics
title: A função s.clearVars()
topic: Desenvolvedor e implementação
uuid: 43 c 425 bc -15 ae -4892-a 5 a 5-e 1 defcb 25 ff 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
>`clearVars()` está incluída no [appmeasurement para javascript](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) , mas não está disponível no código H e versões anteriores.

