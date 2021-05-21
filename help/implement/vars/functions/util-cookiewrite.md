---
title: Util.cookieWrite
description: Grava um valor em um cookie.
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '128'
ht-degree: 100%

---

# Util.cookieWrite

Os cookies podem armazenar e recuperar informações em páginas no mesmo domínio. Use o método `Util.cookieWrite()` para definir um valor de um cookie. Você pode usar o método [`Util.cookieRead()`](util-cookieread.md) para recuperar valores definidos usando `Util.cookieWrite()`.

## Definir cookies no Adobe Experience Platform Launch

O Launch não fornece a capacidade de definir cookies na interface. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.Util.cookieWrite() no AppMeasurement e no editor de código personalizado do Launch

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
