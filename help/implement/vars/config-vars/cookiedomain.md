---
title: cookieDomain
description: (Desativado) Ajuda a determinar o domínio no qual os cookies serão definidos.
feature: Appmeasurement Implementation
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
TQID: https://experienceleague.adobe.com/z6occeGLpxezOj7go2DrwG-j-fc9yBuGyHSmZJK9RfQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 77%

---

# cookieDomain

>[!IMPORTANT]
>Essa variável foi removida. Use [`trackingServer`](trackingserver.md) no lugar dela.

A variável `cookieDomain` determina o domínio no qual o AppMeasurement define cookies. Use essa variável para definir explicitamente o domínio do cookie em vez de usar a variável [`cookieDomainPeriods`](cookiedomainperiods.md).

Essa variável só precisa ser usada quando **ambas** as condições a seguir forem atendidas:

* Se sua implementação usar cookies primários. Essa variável não é necessária com implementações que usam um valor [`trackingServer`](trackingserver.md) que contém `sc.adobedc.net`.
* Se o domínio tiver um ponto no sufixo. Por exemplo, `example.co.uk` poderia usar a variável `cookieDomain` para indicar explicitamente que o domínio do cookie é `example.co.uk`, não `co.uk`.

Somente uma pequena quantidade de implementações tem sido usada para a variável `cookieDomain` e, mesmo assim, variáveis alternativas como [`cookieDomainPeriods`](cookiedomainperiods.md) podem ser usadas.

## Domínio de cookie usando o Web SDK

O Web SDK pode determinar o domínio de armazenamento de cookies correto sem essa variável.

## Domínio de cookie usando a extensão Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.cookieDomain no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `cookieDomain` é uma cadeia de caracteres definida como o domínio no qual você deseja armazenar cookies.

```js
s.cookieDomain = "stats.example.com";
```
