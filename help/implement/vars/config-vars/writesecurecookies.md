---
title: writeSecureCookies
description: Permite que o AppMeasurement defina cookies com o atributo Secure.
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 72%

---

# writeSecureCookies

A variável `writeSecureCookies` permite que o AppMeasurement defina [cookies seguros](https://en.wikipedia.org/wiki/Secure_cookie) para o Analytics. Essa configuração se aplica aos cookies de ID do visitante definidos pelo AppMeasurement e aos cookies definidos pelo método `Util.CookieWrite()`. Ela requer o AppMeasurement versão 2.18.0 ou superior.

`writeSecureCookies` se aplica somente a cookies definidos pelo AppMeasurement JavaScript (`s_fid`, `s_cc` e `s_sq`). Para definir como &#39;seguros&#39; os cookies configurados pela resposta `https` (`s_vi` e `s_ecid`), entre em contato com o Atendimento ao cliente da Adobe.

Saiba mais sobre os cookies do Analytics [aqui](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=pt-BR).

>[!WARNING]
>
>Se você habilitar a variável `writeSecureCookies`, verifique se todo o conteúdo do site está protegido por HTTPS. A coleta de dados não funcionará corretamente se essa variável estiver ativada e você tiver conteúdo inseguro na página.

## Usar cookies seguros com o SDK da Web

Se seu site usa protocolo HTTPS, o atributo Secure é definido para todos os cookies que o SDK da Web define.

## Gravar cookies seguros usando a extensão Adobe Analytics

[!UICONTROL Gravar cookies seguros] é uma caixa de seleção da opção [!UICONTROL Cookies] exibida ao configurar a extensão do Adobe Analytics.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Cookies], que revela a caixa de seleção [!UICONTROL Gravar cookies seguros].

## s.writeSecureCookies no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.writeSecureCookies` é um booliano que determina se o AppMeasurement define o atributo Secure ao criar um cookie. O valor padrão é `false`. Defina essa variável como `true` se todo o conteúdo do site estiver protegido e você desejar que os cookies definidos pelo AppMeasurement tenham o atributo Secure.

```js
s.writeSecureCookies = true;
```
