---
title: Util.cookieWrite
description: Grava um valor em um cookie.
feature: Variables
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 70%

---

# Util.cookieWrite

Os cookies podem armazenar e recuperar informações em páginas no mesmo domínio. Use o método `Util.cookieWrite()` para definir um valor de um cookie. Você pode usar o método [`Util.cookieRead()`](util-cookieread.md) para recuperar valores definidos usando `Util.cookieWrite()`.

## Definir cookies usando a extensão do Adobe Analytics e a extensão SDK da Web

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
