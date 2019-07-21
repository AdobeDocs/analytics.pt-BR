---
description: Grava um valor em um cookie.
keywords: Implementação do Analytics
seo-description: Grava um valor em um cookie.
seo-title: Util.cookieWrite
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Desenvolvedor e implementação
uuid: 8 d 526 e 4 c -6 d 7 a -4119-9434-d 7 ce 4 fbb 7577
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
| value | (opcional) valor para gravar os cookies. |
| expire | (opcional) Objeto Data contendo a data de expiração do cookie. O padrão é usar um cookie de sessão. |

**Retorna:**

**Exemplo:**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```

