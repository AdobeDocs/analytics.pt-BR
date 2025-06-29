---
title: visitorNameSpace
description: (Desativado) Ajudou a determinar o domínio do cookie de terceiros.
feature: Appmeasurement Implementation
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 89%

---

# visitorNamespace

>[!IMPORTANT]
>
>Essa variável foi removida. Use [`trackingServer`](trackingserver.md) no lugar dela.

Em versões anteriores do Adobe Analytics, o AppMeasurement usava a variável `visitorNameSpace` para ajudar a determinar o subdomínio de `2o7.net` onde os cookies do visitante são armazenados. O aumento do uso das práticas de privacidade em navegadores modernos torna os cookies de terceiros menos confiáveis. Com a introdução das variáveis `trackingServer` e [`trackingServerSecure`](trackingserversecure.md), `visitorNameSpace` não é mais necessária.

>[!TIP]
>
>A Adobe recomenda usar cookies próprios no site. Os cookies próprios não usam essa variável.

## Namespace do visitante usando a extensão do Adobe Analytics

[!UICONTROL Namespace do visitante] é um campo sob a opção [!UICONTROL Cookies] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Cookies], que revela o campo [!UICONTROL Namespace do visitante].

A Adobe recomenda não usar esse campo. Use `trackingServer` e `trackingServerSecure` no lugar dele.

## s.visitorNamespace no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.visitorNamespace` é uma string que contém um valor único por organização. As bibliotecas antigas do AppMeasurement incluíam automaticamente esse valor único quando baixadas de versões anteriores do Adobe Analytics. As bibliotecas atuais do AppMeasurement não usam essa variável, a menos que `trackingServer` e `trackingServerSecure` não estejam definidas.

Se sua organização ainda exigir essa variável, escolha um valor que represente sua organização. Você pode armazenar esse valor em um [documento de design da solução](../../prepare/solution-design.md).

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
