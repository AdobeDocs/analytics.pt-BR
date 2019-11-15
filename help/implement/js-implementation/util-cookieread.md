---
description: Obtém o valor de um cookie.
keywords: Analytics Implementation
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Util.cookieRead

Obtém o valor de um cookie.

**Sintaxe:**

```
s.Util.cookieRead(key)
```

**Parâmetros:**

| Parâmetro | Descrição |
|---|---|
| key | (obrigatório) chave para gravar valor em cookies. |

**Devoluções:**

O valor do cookie ou uma string em branco, caso o cookie não seja encontrado.

**Exemplo:**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```

