---
title: Util.cookieWrite
description: Grava um valor em um cookie.
feature: Appmeasurement Implementation
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/VxNoO8-K6rE8NdIgQSA0ubuBwaHXu2OPLCexzNCXdHQ'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 70%

---

# Util.cookieWrite

Os cookies podem armazenar e recuperar informações em páginas no mesmo domínio. Use o método `Util.cookieWrite()` para definir um valor de um cookie. Você pode usar o método [`Util.cookieRead()`](util-cookieread.md) para recuperar valores definidos usando `Util.cookieWrite()`.

## Definir cookies usando a extensão do Adobe Analytics e a extensão do Web SDK

A Coleção de dados da Adobe Experience Platform não fornece a capacidade de definir cookies na interface.

## s.Util.cookieWrite() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Chame o método `s.Util.cookieWrite()` para definir o valor desejado de um cookie.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

Um terceiro argumento opcional está disponível e determina quando o cookie expira. Por padrão, os cookies definidos com o uso de `s.Util.cookieWrite()` expiram no final da sessão do navegador.

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## Exemplos

É possível instanciar uma variável após o sucesso da escrita de um cookie. Essa variável é booleana.

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
