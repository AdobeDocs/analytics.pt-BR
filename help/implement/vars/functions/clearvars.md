---
title: clearVars
description: Apaga os valores a seguir do objeto da instância. Essa função remove os elementos (define-os como "indefinidos").
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# clearVars

Algumas implementações, como em aplicativos de página única, exigem várias ocorrências enviadas no mesmo carregamento de página. Use o `clearVars()` método para apagar os valores de variável para que eles não persistam em ocorrências subsequentes.

Esse método não aceita argumentos e não retorna nenhum valor. Sua única finalidade é apagar valores de variáveis do objeto de instância. Esse método define os seguintes elementos como `undefined`:

* `prop1` - `prop75`
* `eVar` - `eVar250`
* `hier1` - `hier5`
* `list1` - `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Limpar variáveis no Adobe Experience Platform Launch

Defina a ação Limpar variáveis ao configurar uma regra.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Rules] guia e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Actions], clique no ícone &#39;+&#39;
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Clear Variables].

## s.clearVars() no AppMeasurement e Iniciar editor de código personalizado

Você pode chamar o `s.clearVars()` método em qualquer lugar na sua implementação depois de instanciar a instância do objeto do Analytics.

```js
s.clearVars();
```
