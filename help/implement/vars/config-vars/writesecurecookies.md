---
title: writeSecureCookies
description: Permite que o AppMeasurement defina cookies com o atributo Secure.
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: b93cd06c2a8867f4848dc317e426b73dcfbb5dfd
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 84%

---

# writeSecureCookies

A variável `writeSecureCookies` permite que o AppMeasurement defina [cookies seguros](https://en.wikipedia.org/wiki/Secure_cookie) para o Analytics. Essa configuração se aplica aos cookies de ID do visitante definidos pelo AppMeasurement e aos cookies definidos pelo método `Util.CookieWrite()`. Ela requer o AppMeasurement versão 2.18.0 ou superior.

`writeSecureCookies` se aplica somente a cookies definidos pelo AppMeasurement JavaScript (`s_fid`,  `s_cc` e  `s_sq`). Os cookies definidos pela resposta `https` (`s_vi` e `s_ecid`) podem ser definidos como &quot;seguros&quot; ao entrar em contato com o Atendimento ao Cliente do Adobe.

Saiba mais sobre os cookies do Analytics [aqui](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html).

>[!IMPORTANT]
>
>Se você habilitar a variável `writeSecureCookies`, verifique se todo o conteúdo do site está protegido por HTTPS. O AppMeasurement não funcionará se essa variável estiver ativada e você tiver conteúdo não seguro na sua página.

## Gravar cookies seguros no Adobe Experience Platform Launch

[!UICONTROL Gravar cookies seguros] é uma caixa de seleção da opção [!UICONTROL Cookies] exibida ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Cookies], que revela a caixa de seleção [!UICONTROL Gravar cookies seguros].

## s.writeSecureCookies no AppMeasurement e no editor de código personalizado do Launch

A variável `s.writeSecureCookies` é um booliano que determina se o AppMeasurement define o atributo Secure ao criar um cookie. O valor padrão é `false`. Defina essa variável como `true` se todo o conteúdo do site estiver protegido e você desejar que os cookies definidos pelo AppMeasurement tenham o atributo Secure.

```js
s.writeSecureCookies = true;
```
