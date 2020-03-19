---
title: cookieLifetime
description: Substituir a expiração dos cookies criados pelo AppMeasurement.
translation-type: ht
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# cookieLifetime

Os cookies definidos pelo AppMeasurement normalmente expiram em 2 anos. Use a variável `cookieLifetime` para substituir a data de expiração dos cookies definidos pelo AppMeasurement.

> [!NOTE] Essa variável afeta a contagem e atribuição de visitantes únicos. Tenha cuidado ao definir essa variável.

## Vida útil do cookie no Adobe Experience Platform Launch

A Vida útil do cookie é uma lista suspensa da opção [!UICONTROL Cookies] ao configurar a extensão Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Cookies], que revela a lista suspensa [!UICONTROL Vida útil do cookie].

Essa lista suspensa contém os seguintes valores:

* **Padrão**: o cookie expira após 2 anos.
* **Nenhum**: o AppMeasurement não define cookies.
* **Sessão**: o cookie expira ao final da sessão do visitante.
* **Segundos**: o cookie expira após o número especificado de segundos decorrido. Por exemplo, definir essa lista suspensa como [!UICONTROL Segundos] e colocar `86400` no campo personalizado força os cookies a expirarem após exatamente 24 horas.

## s.cookieLifetime no AppMeasurement e no editor de código personalizado do Launch

A variável `s.cookieLifetime` é uma cadeia de caracteres que determina a data de expiração dos cookies definidos pelo AppMeasurement.

* Se definida como `SESSION`, os cookies definidos pelo AppMeasurement expirarão após a conclusão da sessão do navegador.
* Se definida como `NONE`, o AppMeasurement não tentará definir cookies.
* Se definida como uma cadeia de caracteres de número inteiro, os cookies definidos pelo AppMeasurement expirarão após o número especificado de segundos decorrido.

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";

