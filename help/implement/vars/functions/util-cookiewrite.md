---
title: Util.cookieWrite
description: Grava um valor para um cookie.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Util.cookieWrite

Os cookies podem armazenar e recuperar informações em páginas no mesmo domínio. Use o `Util.cookieWrite` método para definir um valor para um cookie. Você pode usar o `Util.cookieRead` método para recuperar valores definidos usando `Util.cookieWrite`.

## Definir cookies no Adobe Experience Platform Launch

O Launch não fornece a capacidade de definir cookies na interface. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.Util.cookieWrite() no AppMeasurement e Iniciar editor de código personalizado

Chame o `s.Util.cookieWrite()` método para definir um cookie para um valor desejado.

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

Um terceiro argumento opcional está disponível e determina quando o cookie expira. Por padrão, os cookies definidos com o uso `s.Util.cookieWrite()` expiram no final da sessão do navegador.

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## Exemplos

É possível instanciar uma variável após o sucesso de escrever um cookie. Essa variável é booleana.

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```
