---
title: writeSecureCookies
description: Permite que o AppMeasurement defina cookies com o atributo Secure.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 100%

---


# writeSecureCookies

A variável `writeSecureCookies` permite que o AppMeasurement defina [cookies seguros](https://en.wikipedia.org/wiki/Secure_cookie) para o Analytics. Essa configuração se aplica aos cookies de ID do visitante definidos pelo AppMeasurement e aos cookies definidos pelo método `Util.CookieWrite()`. Ela requer o AppMeasurement versão 2.18.0 ou superior.

>[!IMPORTANT]
>
>Se você habilitar a variável `writeSecureCookies`, verifique se todo o conteúdo do site está protegido por HTTPS. O AppMeasurement não funcionará se essa variável estiver ativada e você tiver conteúdo não seguro na sua página.

## Gravar cookies seguros no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.writeSecureCookies no AppMeasurement e no editor de código personalizado do Launch

A variável `s.writeSecureCookies` é um booliano que determina se o AppMeasurement define o atributo Secure ao criar um cookie. O valor padrão é `false`. Defina essa variável como `true` se todo o conteúdo do site estiver protegido e você desejar que os cookies definidos pelo AppMeasurement tenham o atributo Secure.

```js
s.writeSecureCookies = true;
```
