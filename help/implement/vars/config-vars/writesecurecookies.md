---
title: writeSecureCookies
description: Permite que o AppMeasurement defina cookies com o atributo Secure.
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 100%

---

# writeSecureCookies

A variável `writeSecureCookies` permite que o AppMeasurement defina [cookies seguros](https://en.wikipedia.org/wiki/Secure_cookie) para o Analytics. Essa configuração se aplica aos cookies de ID do visitante definidos pelo AppMeasurement e aos cookies definidos pelo método `Util.CookieWrite()`. Ela requer o AppMeasurement versão 2.18.0 ou superior.

`writeSecureCookies` se aplica somente a cookies definidos pelo AppMeasurement JavaScript (`s_fid`, `s_cc` e `s_sq`). Para definir como &#39;seguros&#39; os cookies configurados pela resposta `https` (`s_vi` e `s_ecid`), entre em contato com o Atendimento ao cliente da Adobe.

Saiba mais sobre os cookies do Analytics [aqui](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=pt-BR).

>[!WARNING]
>
>Se você habilitar a variável `writeSecureCookies`, verifique se todo o conteúdo do site está protegido por HTTPS. O AppMeasurement não funcionará se essa variável estiver ativada e você tiver conteúdo não seguro na sua página.

## Gravar cookies seguros usando tags na Adobe Experience Platform

[!UICONTROL Gravar cookies seguros] é uma caixa de seleção da opção [!UICONTROL Cookies] exibida ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Interface da coleção de dados](https://experience.adobe.com/data-collection) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Cookies], que revela a caixa de seleção [!UICONTROL Gravar cookies seguros].

## s.writeSecureCookies no AppMeasurement e no editor de código personalizado do

A variável `s.writeSecureCookies` é um booliano que determina se o AppMeasurement define o atributo Secure ao criar um cookie. O valor padrão é `false`. Defina essa variável como `true` se todo o conteúdo do site estiver protegido e você desejar que os cookies definidos pelo AppMeasurement tenham o atributo Secure.

```js
s.writeSecureCookies = true;
```
