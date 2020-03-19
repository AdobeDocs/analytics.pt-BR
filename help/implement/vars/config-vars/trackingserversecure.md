---
title: trackingServerSecure
description: Determine se as solicitações de imagem de localização são enviadas em páginas HTTPS.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackingServerSecure

A Adobe coleta dados em seu site recebendo uma solicitação de imagem gerada pelo visitante. A `trackingServerSecure` variável determina o local em que uma solicitação de imagem é enviada por HTTPS. Também determina o local em que os cookies do visitante são armazenados. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

> [!IMPORTANT] Alterar esse valor faz com que o AppMeasurement procure cookies em um local diferente. A contagem de visitantes únicos pode aumentar temporariamente no relatório, já que os cookies do visitante são definidos no novo local.

## Servidor de rastreamento SSL no Adobe Experience Platform Launch

[!UICONTROL SSL Tracking Server] é um campo sob o [!UICONTROL General] acordeão ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão em Adobe Analytics.
4. Amplie o [!UICONTROL General] acordeão, que revela o [!UICONTROL SSL Tracking Server] campo.

Se esse campo ficar em branco, o padrão será o valor na [`trackingServer`](trackingserver.md) variável.

## s.trackingServerSecure no AppMeasurement e Iniciar editor de código personalizado

A `s.trackingServerSecure` variável é uma string que contém o local para enviar solicitações de imagem. É quase sempre um subdomínio do site. Práticas de privacidade modernas em navegadores geralmente tornam cookies de terceiros não confiáveis. Se essa variável estiver em branco, ela usará o valor na `s.trackingServer` variável.

O valor dessa variável é quase sempre um domínio próprio, como `data.example.com`. Consulte Cookies [primários na Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) no guia do usuário dos principais serviços para obter mais informações sobre o processo de cookies primários.

O indivíduo que inicialmente configura a implementação do cookie primário também define o domínio e o subdomínio usados. Por exemplo:

```js
s.trackingServerSecure = "data.example.com";
```

Os registros CNAME normalmente apontam para um subdomínio em `ssl.d1.sc.omtrdc.net`.
