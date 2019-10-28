---
description: Obtém o valor de um cookie.
keywords: Implementação do Analytics
seo-description: Obtém o valor de um cookie.
seo-title: Util.cookieRead
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Desenvolvedor e implementação
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

**Retorna:**

O valor do cookie ou uma string em branco, caso o cookie não seja encontrado.

**Exemplo:**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```

