---
title: cookieLifetime
description: Substituir a expiração dos cookies criados pelo AppMeasurement.
feature: Appmeasurement Implementation
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
TQID: https://experienceleague.adobe.com/QWYqMdVf7Zl0FIw25NuquxYP-T7bGCZEd-67OzrRzpg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 63%

---

# cookieLifetime

Os cookies definidos pelo AppMeasurement normalmente expiram em 2 anos. Use a variável `cookieLifetime` para substituir a data de expiração dos cookies definidos pelo AppMeasurement.

>[!NOTE]
>
>Essa variável afeta a contagem e atribuição de visitantes únicos. Tenha cuidado ao definir essa variável.

## Duração do cookie usando o Web SDK

O Web SDK ainda não oferece personalização ao tempo de vida dos cookies definidos.

## Duração do cookie usando a extensão Adobe Analytics

A Vida útil do cookie é uma lista suspensa da opção [!UICONTROL Cookies] ao configurar a extensão Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
1. Expanda a opção [!UICONTROL Cookies], que revela a lista suspensa [!UICONTROL Vida útil do cookie].

Essa lista suspensa contém os seguintes valores:

* **Padrão**: o cookie expira após 2 anos.
* **Nenhum**: o AppMeasurement não define cookies.
* **Sessão**: o cookie expira ao final da sessão do visitante.
* **Segundos**: o cookie expira após o número especificado de segundos decorrido. Por exemplo, definir essa lista suspensa como [!UICONTROL Segundos] e colocar `86400` no campo personalizado força os cookies a expirarem após exatamente 24 horas.

## s.cookieLifetime no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.cookieLifetime` é uma cadeia de caracteres que determina a data de expiração dos cookies definidos pelo AppMeasurement.

* Se definida como `SESSION`, os cookies definidos pelo AppMeasurement expirarão após a conclusão da sessão do navegador.
* Se definida como `NONE`, o AppMeasurement não tentará definir cookies.
* Se definida como uma cadeia de caracteres de número inteiro, os cookies definidos pelo AppMeasurement expirarão após o número especificado de segundos decorrido.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
