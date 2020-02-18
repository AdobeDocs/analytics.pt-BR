---
title: writeSecureCookies
description: Permite que o AppMeasurement defina cookies com o atributo Secure.
translation-type: tm+mt
source-git-commit: 117a3c1ad411b25d8277b5678915b76eadd232a7

---


# writeSecureCookies

A `writeSecureCookies` variável permite que o AppMeasurement defina cookies [](https://en.wikipedia.org/wiki/Secure_cookie) seguros para o Analytics. Essa configuração se aplica aos cookies de ID de visitante definidos pelo AppMeasurement e aos cookies definidos pelo `Util.CookieWrite` método. Ela requer o AppMeasurement 2.18.0 ou superior.

> [!NOTE] Se você ativar a `writeSecureCookies` variável, verifique se todo o conteúdo do site está protegido contra HTTPS.

## Gravar cookies seguros no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.writeSecureCookies no AppMeasurement e Iniciar editor de código personalizado

A `s.writeSecureCookies` variável é um booliano que determina se o AppMeasurement define o atributo Secure ao criar um cookie. Its default value is `false`. Defina essa variável para `true` se todo o conteúdo do site estiver protegido e você desejar que os cookies definidos pelo AppMeasurement tenham o atributo Secure.

```js
s.writeSecureCookies = true;
```
