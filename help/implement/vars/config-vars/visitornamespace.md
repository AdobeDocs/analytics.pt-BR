---
title: visitorNameSpace
description: (Desativado) Ajudou a determinar o domínio do cookie de terceiros.
feature: Appmeasurement Implementation
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
TQID: https://experienceleague.adobe.com/y9oXzSzgN-s8gVrdHs0nFRm0ASSbUPzlkW-V6u1GnMg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
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
