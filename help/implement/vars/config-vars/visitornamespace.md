---
title: visitorNameSpace
description: Variável aposentada que determinou o domínio do cookie.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# visitorNamespace

> [!IMPORTANT] Essa variável é removida. Use [`trackingServer`](trackingserver.md) em vez disso.

Em versões anteriores do Adobe Analytics, o AppMeasurement usava a `visitorNameSpace` variável para ajudar a determinar o subdomínio de `2o7.net` onde os cookies do visitante são armazenados. O aumento das práticas de privacidade em navegadores modernos torna os cookies de terceiros menos confiáveis. Com a introdução das variáveis `trackingServer` e [`trackingServerSecure`](trackingserversecure.md) , não `visitorNameSpace` é mais necessário.

> [!TIP] A Adobe recomenda usar cookies primários em seu site. Os cookies primários não usam essa variável.

## Namespace do visitante no Adobe Experience Platform Launch

[!UICONTROL Visitor Namespace] é um campo sob o [!UICONTROL Cookies] acordeão ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão em Adobe Analytics.
4. Amplie o [!UICONTROL Cookies] acordeão, que revela o [!UICONTROL Visitor Namespace] campo.

A Adobe recomenda não usar esse campo. Use `trackingServer` e `trackingServerSecure` em vez disso.

## s.visitorNamespace no AppMeasurement e no editor de código personalizado Iniciar

A `s.visitorNamespace` variável é uma string que contém um valor exclusivo por organização. As bibliotecas antigas do AppMeasurement incluíam automaticamente esse valor único quando baixadas de versões anteriores do Adobe Analytics. As bibliotecas atuais do AppMeasurement não usam essa variável, a menos que `trackingServer` e `trackingServerSecure` não estejam definidas.

Se sua organização ainda exigir essa variável, escolha um valor que represente sua organização. Você pode armazenar esse valor em um documento [de design de](../../prepare/solution-design.md)solução.

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
