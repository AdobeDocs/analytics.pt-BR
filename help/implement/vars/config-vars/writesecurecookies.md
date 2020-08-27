---
title: writeSecureCookies
description: Permite que o AppMeasurement defina cookies com o atributo Secure.
translation-type: tm+mt
source-git-commit: defb701d01747685a421b89a553f47efe40f1432
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 86%

---


# writeSecureCookies

A variável `writeSecureCookies` permite que o AppMeasurement defina [cookies seguros](https://en.wikipedia.org/wiki/Secure_cookie) para o Analytics. Essa configuração se aplica aos cookies de ID do visitante definidos pelo AppMeasurement e aos cookies definidos pelo método `Util.CookieWrite()`. Ela requer o AppMeasurement versão 2.18.0 ou superior.

>[!IMPORTANT]
>
>Se você habilitar a variável `writeSecureCookies`, verifique se todo o conteúdo do site está protegido por HTTPS. O AppMeasurement não funcionará se essa variável estiver ativada e você tiver conteúdo não seguro na sua página.

## Gravar cookies seguros no Adobe Experience Platform Launch

[!UICONTROL A opção Gravar cookies] protegidos é uma caixa de seleção na opção [!UICONTROL Cookies] ao configurar a extensão Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] no Adobe Analytics.
4. Expanda o acordeão [!UICONTROL Cookies] , que revela a caixa de seleção [!UICONTROL Gravar cookies] protegidos.

## s.writeSecureCookies no AppMeasurement e no editor de código personalizado do Launch

A variável `s.writeSecureCookies` é um booliano que determina se o AppMeasurement define o atributo Secure ao criar um cookie. O valor padrão é `false`. Defina essa variável como `true` se todo o conteúdo do site estiver protegido e você desejar que os cookies definidos pelo AppMeasurement tenham o atributo Secure.

```js
s.writeSecureCookies = true;
```
