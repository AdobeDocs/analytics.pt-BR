---
title: visitorNameSpace
description: Variável aposentada que determinou o domínio do cookie.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorNamespace

> [!IMPORTANT] Essa variável é removida. Use `trackingServer` em vez disso.

Em versões anteriores do Adobe Analytics, o AppMeasurement usava a `visitorNameSpace` variável para ajudar a determinar o subdomínio de `2o7.net` onde os cookies do visitante são armazenados.  O aumento das práticas de privacidade em navegadores modernos torna os cookies de terceiros menos confiáveis. Com a introdução das variáveis `trackingServer` e `trackingServerSecure` , não `visitorNameSpace` é mais necessário.

> [!TIP] A Adobe recomenda usar cookies primários em seu site. Os cookies primários não usam essa variável.

## Namespace do visitante no Adobe Experience Platform Launch

[!UICONTROL O namespace] do visitante é um campo sob a opção [!UICONTROL Cookies] ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda o acordeão [!UICONTROL Cookies] , que revela o campo Namespace [!UICONTROL do] visitante.

A Adobe recomenda não usar esse campo. Use `trackingServer` e `trackingServerSecure` em vez disso.

## s.visitorNamespace no AppMeasurement e no editor de código personalizado Iniciar

A `s.visitorNamespace` variável é uma string que contém um valor exclusivo por organização. As bibliotecas antigas do AppMeasurement incluíam automaticamente esse valor único quando baixadas de versões anteriores do Adobe Analytics. As bibliotecas atuais do AppMeasurement não usam essa variável, a menos que `trackingServer` e `trackingServerSecure` não estejam definidas.

Se sua organização ainda exigir essa variável, escolha um valor que represente sua organização. Você pode armazenar esse valor em um documento [de design de](../../prepare/solution-design.md)solução.

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
