---
title: visitorNameSpace
description: Variável removida que determinava o domínio do cookie.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# visitorNamespace

>[!IMPORTANT] Essa variável foi removida. Use [`trackingServer`](trackingserver.md) no lugar dela.

Em versões anteriores do Adobe Analytics, o AppMeasurement usava a variável `visitorNameSpace` para ajudar a determinar o subdomínio de `2o7.net` onde os cookies do visitante são armazenados. O aumento do uso das práticas de privacidade em navegadores modernos torna os cookies de terceiros menos confiáveis. Com a introdução das variáveis `trackingServer` e [`trackingServerSecure`](trackingserversecure.md), `visitorNameSpace` não é mais necessária.

>[!TIP] A Adobe recomenda usar cookies próprios no site. Os cookies próprios não usam essa variável.

## Namespace do visitante no Adobe Experience Platform Launch

[!UICONTROL Visitor Namespace] é um campo sob o [!UICONTROL Cookies] acordeão ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Amplie o [!UICONTROL Cookies] acordeão, que revela o [!UICONTROL Visitor Namespace] campo.

A Adobe recomenda não usar esse campo. Use `trackingServer` e `trackingServerSecure` no lugar dele.

## s.visitorNamespace no AppMeasurement e no editor de código personalizado do Launch

A variável `s.visitorNamespace` é uma string que contém um valor exclusivo por organização. As bibliotecas antigas do AppMeasurement incluíam automaticamente esse valor único quando baixadas de versões anteriores do Adobe Analytics. As bibliotecas atuais do AppMeasurement não usam essa variável, a menos que `trackingServer` e `trackingServerSecure` não estejam definidas.

Se sua organização ainda exigir essa variável, escolha um valor que represente sua organização. Você pode armazenar esse valor em um [documento de design da solução](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
