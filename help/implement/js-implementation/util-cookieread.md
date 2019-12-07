---
description: Obtém o valor de um cookie.
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

