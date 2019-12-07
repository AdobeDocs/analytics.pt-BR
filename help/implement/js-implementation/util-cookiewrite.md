---
description: Grava um valor em um cookie.
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Developer and implementation
uuid: 8d526e4c-6d7a-4119-9434-d7ce4fbb7577
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieWrite

Grava um valor em um cookie.

**Sintaxe:**

```
s.Util.cookieWrite(key, value [,expire])
```

**Parâmetros:**

| Parâmetro | Descrição |
|---|---|
| key | (obrigatório) chave para gravar valor em cookies. |
| valor | (opcional) valor para gravar os cookies. |
| expire | (opcional) Objeto Data contendo a data de expiração do cookie. O padrão é usar um cookie de sessão. |

**Devoluções:**

**Exemplo:**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```

