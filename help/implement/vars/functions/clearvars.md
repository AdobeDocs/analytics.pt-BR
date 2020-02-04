---
title: clearVars
description: Apaga os valores a seguir do objeto da instância. Essa função remove os elementos (define-os como "indefinidos").
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# clearVars

Algumas implementações, como em aplicativos de página única, exigem várias ocorrências enviadas no mesmo carregamento de página. Use o `clearVars` método para apagar os valores de variável para que eles não persistam em ocorrências subsequentes.

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
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique no ícone &#39;+&#39;
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Limpar variáveis].

## s.clearVars() no AppMeasurement e Iniciar editor de código personalizado

Você pode chamar o `s.clearVars()` método em qualquer lugar na implementação depois de instanciar a instância do objeto do Analytics.

```js
s.clearVars();
```
