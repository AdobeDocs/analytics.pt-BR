---
title: clearVars
description: Limpar valores do objeto da instância.
feature: Appmeasurement Implementation
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
role: Admin, Developer
TQID: https://experienceleague.adobe.com/oZOgS1REUIwiLCwM1URlDy7rkpmeM59hrkOX7DBVVcE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 191
ht-degree: 68%

---

# clearVars

Algumas implementações, como aquelas em aplicativos de página única, exigem que várias ocorrências sejam enviadas no mesmo carregamento de página. Use o método `clearVars()` para apagar os valores de variáveis para que elas não persistam em ocorrências subsequentes.

Esse método não aceita argumentos e não retorna nenhum valor. Sua única finalidade é apagar valores de variáveis do objeto instanciado. Esse método define os seguintes elementos como `undefined`:

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

## Limpar variáveis usando o Web SDK

Ao enviar dados para a Adobe usando a Web SDK, todos os dados XDM são apagados automaticamente.

## Limpar variáveis usando a extensão do Adobe Analytics

Defina a ação Limpar variáveis ao configurar uma regra.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique no ícone “+”
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de Ação] como [!UICONTROL Limpar Variáveis].

## s.clearVars() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Você pode chamar o método `s.clearVars()` em qualquer lugar na implementação depois de criar a instância do objeto do Analytics.

```js
s.clearVars();
```
