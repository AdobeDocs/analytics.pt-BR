---
title: cookieLifetime
description: Substituir a expiração dos cookies criados pelo AppMeasurement.
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 64%

---

# cookieLifetime

Os cookies definidos pelo AppMeasurement normalmente expiram em 2 anos. Use a variável `cookieLifetime` para substituir a data de expiração dos cookies definidos pelo AppMeasurement.

>[!NOTE]
>
>Essa variável afeta a contagem e atribuição de visitantes únicos. Tenha cuidado ao definir essa variável.

## Duração do cookie usando o SDK da Web

O SDK da Web ainda não oferece personalização para a duração dos cookies que define.

## Duração do cookie usando a extensão Adobe Analytics

A Vida útil do cookie é uma lista suspensa na [!UICONTROL Cookies] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
1. Expanda o [!UICONTROL Cookies] , que revela o [!UICONTROL Duração do cookie] lista suspensa.

Essa lista suspensa contém os seguintes valores:

* **Padrão**: o cookie expira após 2 anos.
* **Nenhum**: o AppMeasurement não define cookies.
* **Sessão**: o cookie expira ao final da sessão do visitante.
* **Segundos**: o cookie expira após o número especificado de segundos decorrido. Por exemplo, definir essa lista suspensa como [!UICONTROL Seconds] e colocação `86400` no campo personalizado força os cookies a expirarem após exatamente 24 horas.

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
