---
title: cookieLifetime
description: Substitua a expiração dos cookies criados pelo AppMeasurement.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# cookieLifetime

Os cookies definidos pelo AppMeasurement normalmente expiram em 2 anos. Use a `cookieLifetime` variável para substituir a data de expiração dos cookies definidos pelo AppMeasurement.

> [!NOTE] Essa variável afeta a contagem e atribuição de visitantes únicos. Tenha cuidado ao definir essa variável.

## Vida útil do cookie no lançamento da plataforma Adobe Experience

A Vida útil do cookie é uma lista suspensa sob a opção [!UICONTROL Cookies] ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda o acordeão [!UICONTROL Cookies] , que revela a lista suspensa [!UICONTROL Vida útil] do cookie.

Esta lista suspensa contém os seguintes valores:

* **Padrão**: O cookie expira após 2 anos.
* **Nenhum**: O AppMeasurement não define cookies.
* **Sessão**: O cookie expira no final da sessão do visitante.
* **Segundos**: O cookie expira após o número especificado de segundos decorrido. Por exemplo, definir essa lista suspensa como [!UICONTROL Segundos] e colocar `86400` no campo personalizado força os cookies a expirarem após exatamente 24 horas.

## s.cookieLifetime no AppMeasurement e no editor de código personalizado Iniciar

A `s.cookieLifetime` variável é uma string que determina a data de expiração dos cookies definidos pelo AppMeasurement.

* Se definido como `SESSION`, os cookies definidos pelo AppMeasurement expirarão após a conclusão da sessão do navegador.
* Se definido como `NONE`, o AppMeasurement não tentará definir cookies.
* Se estiver definido como uma string de número inteiro, os cookies definidos pelo AppMeasurement expirarão após o número especificado de segundos decorrido.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";

