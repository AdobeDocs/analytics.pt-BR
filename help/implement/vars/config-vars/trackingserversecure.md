---
title: trackingServerSecure
description: Defina para que local as solicitações de imagem são enviadas em páginas HTTPS.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# trackingServerSecure

A Adobe coleta dados em seu site recebendo uma solicitação de imagem gerada pelo visitante. A variável `trackingServerSecure` determina o local para onde uma solicitação de imagem é enviada por HTTPS. Também determina o local em que os cookies do visitante são armazenados. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

>[!IMPORTANT] Alterar esse valor faz com que o AppMeasurement procure cookies em um local diferente. A contagem de visitantes únicos pode aumentar temporariamente no relatório, já que os cookies de visitantes estão definidos para serem enviados ao novo local.

## Servidor de rastreamento SSL no Adobe Experience Platform Launch

[!UICONTROL SSL Tracking Server] é um campo sob o [!UICONTROL General] acordeão ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Amplie o [!UICONTROL General] acordeão, que revela o [!UICONTROL SSL Tracking Server] campo.

Se esse campo ficar em branco, o padrão será o valor na variável [`trackingServer`](trackingserver.md).

## s.trackingServerSecure no AppMeasurement e no editor de código personalizado do Launch

A varável `s.trackingServerSecure` é uma string que contém o local para o envio de solicitações de imagem. É quase sempre um subdomínio do seu site. Geralmente, práticas de privacidade modernas em navegadores tornam cookies de terceiros não confiáveis. Se essa variável estiver em branco, ela usará o valor na variável `s.trackingServer`.

O valor dessa variável é quase sempre um domínio próprio, como `data.example.com`. Consulte [Cookies próprios na Experience Cloud](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-first-party.html) no guia do usuário dos serviços principais para obter mais informações sobre o processo de configuração de cookies próprios.

O indivíduo que configura inicialmente a implementação do cookie próprio também define o domínio e o subdomínio que são usados. Por exemplo:

```js
s.trackingServerSecure = "data.example.com";
```

Os registros CNAME normalmente apontam para um subdomínio em `ssl.d1.sc.omtrdc.net`.
