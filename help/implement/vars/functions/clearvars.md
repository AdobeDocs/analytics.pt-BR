---
title: clearVars
description: Apaga os valores a seguir do objeto da instância. Essa função remove os elementos (define-os como "indefinidos").
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 87%

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

## Limpar variáveis usando tags no Adobe Experience Platform

Defina a ação Limpar variáveis ao configurar uma regra.

1. Faça logon na [Interface do usuário da coleta de dados](https://experience.adobe.com/data-collection) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique no ícone “+”
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Limpar variáveis].

## s.clearVars() no AppMeasurement e no editor de código personalizado do 

Você pode chamar o método `s.clearVars()` em qualquer lugar na implementação depois de criar a instância do objeto do Analytics.

```js
s.clearVars();
```
