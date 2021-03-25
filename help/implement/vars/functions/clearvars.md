---
title: clearVars
description: Limpar valores de variável do objeto de rastreamento.
translation-type: tm+mt
source-git-commit: f19be69832b0a2b723d825472e0eec1e44f89440
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# clearVars

Algumas implementações, como aquelas em aplicativos de página única, exigem que várias ocorrências sejam enviadas no mesmo carregamento de página. Use o método `clearVars()` para apagar os valores de variáveis para que elas não persistam em ocorrências subsequentes.

Esse método não aceita argumentos e não retorna nenhum valor. Sua única finalidade é apagar valores de variáveis do objeto instanciado. Esse método define os seguintes elementos como `undefined`:

* `prop1` - `prop75`
* `eVar` -  `eVar250`
* `hier1` -  `hier5`
* `list1` -  `list3`
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

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique no ícone “+”
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Limpar variáveis].

## s.clearVars() no AppMeasurement e no editor de código personalizado do Launch

Você pode chamar o método `s.clearVars()` em qualquer lugar na implementação depois de criar a instância do objeto do Analytics.

```js
s.clearVars();
```
