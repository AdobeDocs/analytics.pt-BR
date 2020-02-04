---
title: trackingServer
description: Determine se as solicitações de imagem de localização são enviadas.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServer

A Adobe coleta dados em seu site recebendo uma solicitação de imagem gerada pelo visitante. A `trackingServer` variável determina o local em que uma solicitação de imagem é enviada. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

> [!IMPORTANT] Alterar esse valor faz com que o AppMeasurement procure cookies em um local diferente. A contagem de visitantes únicos pode aumentar temporariamente no relatório, já que os cookies do visitante são definidos no novo local.

## Servidor de rastreamento no Adobe Experience Platform Launch

O Servidor de rastreamento é um campo sob a opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda o acordeão [!UICONTROL Geral] , que revela o campo Servidor [!UICONTROL de] rastreamento.

Se esse campo ficar em branco, o padrão será `[rsid].112.2o7.net`.

## s.trackingServer no AppMeasurement e no editor de código personalizado Iniciar

A `s.trackingServer` variável é uma string que contém o local para enviar dados.

> [!TIP] Algumas implementações apontam dados para `2o7.net`. Embora este seja um domínio de coleta de dados válido, ele não usa a coleta de dados regionais. Implementações que usam tempos de resposta de solicitação de imagem ligeiramente mais altos. `2o7.net`

## Determine o valor para trackingServer

O valor dessa variável depende do uso de cookies primários ou cookies de terceiros. A Adobe recomenda usar cookies primários em sua implementação.

### Cookies próprios

Se você usar uma implementação de cookie primário, é provável que alguém em sua organização já tenha concluído o processo de cookie primário. Consulte Cookies [primários na Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) no guia do usuário dos principais serviços para obter mais informações sobre o processo de cookies primários.

O indivíduo que inicialmente configura a implementação do cookie primário também define o domínio e o subdomínio usados. Por exemplo:

```js
s.trackingServer = "data.example.com";
```

Normalmente, os registros CNAME já estão configurados e apontam para `sc.omtrdc.net`. O domínio também `2o7.net` é um destino CNAME válido, usado principalmente em versões anteriores do Adobe Analytics.

### Cookies de terceiros

> [!TIP] O aumento das práticas de privacidade em navegadores modernos torna os cookies de terceiros menos confiáveis. A Adobe recomenda seguir o fluxo de trabalho do cookie primário.

Se você usar uma implementação de cookie de terceiros, o valor para `trackingServer` será um subdomínio de `sc.omtrdc.net`. Por exemplo:

```js
s.trackingServer = "example.sc.omtrdc.net";
```

Escolha um subdomínio exclusivo da sua organização, que provavelmente não será escolhido por outra organização que use o Adobe Analytics. Verifique se todas as implementações em sua organização usam o mesmo servidor de rastreamento. Pode ser útil manter essas informações em um documento [de design de](../../prepare/solution-design.md)solução.
