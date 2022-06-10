---
title: trackingServer
description: Defina para que local as solicitações de imagens são enviadas.
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 69%

---

# trackingServer

A Adobe coleta dados em seu site recebendo uma solicitação de imagem gerada pelo visitante. A variável `trackingServer` determina para que local uma solicitação de imagem é enviada. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

>[!WARNING]
>
>Alterar esse valor faz com que o AppMeasurement procure cookies em um local diferente. A contagem de visitantes únicos pode aumentar temporariamente no relatório, já que os cookies de visitantes estão definidos para serem enviados ao novo local.

## Domínio de borda usando a extensão SDK da Web

O SDK da Web usa [!UICONTROL Domínio de borda] para lidar com o Servidor de rastreamento e o Servidor de rastreamento seguro. É possível definir a [!UICONTROL Domínio de borda] ao configurar a extensão do SDK da Web.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para o [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** botão abaixo [!UICONTROL Adobe Experience Platform Web SDK].
1. Defina as **[!UICONTROL Domínio de borda]** campo de texto.

Consulte [Configurar a extensão Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) na documentação do SDK da Web para obter mais informações.

>[!TIP]
>
>Se sua organização mudar para o SDK da Web a partir de uma implementação de extensão do AppMeasurement ou do Analytics, esse campo poderá usar o mesmo valor contido em `trackingServerSecure` ou `trackingServer`).

## Domínio de borda que implementa manualmente o SDK da Web

Configurar o SDK usando [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR). O campo é uma string que determina o domínio para o qual enviar dados.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Servidor de rastreamento usando a extensão Adobe Analytics

Servidor de rastreamento é um campo sob a opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Servidor de rastreamento].

Se esse campo ficar em branco, o padrão será `[rsid].data.adobedc.net`.

## s.trackingServer no AppMeasurement e no editor de código personalizado da extensão do Analytics

A varável `s.trackingServer` é uma string que contém o local para o envio de dados.

## Determine o valor de `trackingServer`

O valor dessa variável depende do uso de cookies próprios ou de cookies de terceiros. A Adobe recomenda usar cookies próprios na implementação.

### Cookies próprios

Se você usar uma implementação com cookies próprios, é provável que alguém em sua organização já tenha concluído o processo de configuração de cookie próprio. Consulte [Cookies próprios na Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=pt-BR) no guia do usuário dos serviços principais para obter mais informações sobre o processo de configuração de cookies próprios.

O indivíduo que configura inicialmente a implementação do cookie próprio também define o domínio e o subdomínio que são usados. Por exemplo:

```js
s.trackingServer = "data.example.com";
```

### Cookies de terceiros

>[!TIP]
>
>O aumento do uso das práticas de privacidade em navegadores modernos torna os cookies de terceiros menos confiáveis. A Adobe recomenda seguir o fluxo de trabalho do cookie próprio.

Se você usar uma implementação com cookies de terceiros, o valor de `trackingServer` será um subdomínio de `data.adobedc.net`. Por exemplo:

```js
s.trackingServer = "example.data.adobedc.net";
```

Escolha um subdomínio exclusivo da sua organização, um que provavelmente não será escolhido por outra organização que usa o Adobe Analytics.  O namespace do visitante atribuído à sua organização é recomendado.  Verifique se todas as implementações em sua organização usam o mesmo servidor de rastreamento. Pode ser útil manter essas informações em um [documento de design da solução](../../prepare/solution-design.md).

Sua organização pode já estar usando um servidor de rastreamento de terceiros nos domínios `sc.omtrdc.net` ou `2o7.net`.  Elas foram usadas principalmente em versões anteriores do Adobe Analytics e ainda são válidas.

>[!NOTE]
>
>Não use subdomínios mais profundos do que `example.data.adobedc.net`. Por exemplo, `custom.example.data.adobedc.net` não é um servidor de rastreamento válido.
