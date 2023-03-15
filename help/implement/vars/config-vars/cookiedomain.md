---
title: cookieDomain
description: A variável cookieDomain ajuda a determinar o domínio no qual os cookies serão definidos.
feature: Variables
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 81%

---

# cookieDomain

>[!IMPORTANT]
>
>Essa variável foi removida. Use [`trackingServer`](trackingserver.md) no lugar dela.

A variável `cookieDomain` determina o domínio no qual o AppMeasurement define cookies. Use essa variável para definir explicitamente o domínio do cookie em vez de usar a variável [`cookieDomainPeriods`](cookiedomainperiods.md).

Essa variável só precisa ser usada quando **ambas** as condições a seguir forem atendidas:

* Se sua implementação usar cookies primários. Essa variável não é necessária com implementações que usam um valor [`trackingServer`](trackingserver.md) que contém `sc.adobedc.net`.
* Se o domínio tiver um ponto no sufixo. Por exemplo, `example.co.uk` poderia usar a variável `cookieDomain` para indicar explicitamente que o domínio do cookie é `example.co.uk`, não `co.uk`.

Somente uma pequena quantidade de implementações tem sido usada para a variável `cookieDomain` e, mesmo assim, variáveis alternativas como [`cookieDomainPeriods`](cookiedomainperiods.md) podem ser usadas.

## Domínio de cookie usando o SDK da Web

O SDK da Web pode determinar o domínio de armazenamento de cookies correto sem essa variável.

## Domínio de cookie usando a extensão Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.cookieDomain no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `cookieDomain` é uma cadeia de caracteres definida como o domínio no qual você deseja armazenar cookies.

```js
s.cookieDomain = "stats.example.com";
```
