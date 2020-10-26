---
title: trackingServer
description: Defina para que local as solicitações de imagens são enviadas.
translation-type: tm+mt
source-git-commit: d9fa9fa6afb6b76ae37a92c86d9ca21a9c3fb22e
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 91%

---


# trackingServer

A Adobe coleta dados em seu site recebendo uma solicitação de imagem gerada pelo visitante. A variável `trackingServer` determina para que local uma solicitação de imagem é enviada. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

>[!IMPORTANT]
>
>Alterar esse valor faz com que o AppMeasurement procure cookies em um local diferente. A contagem de visitantes únicos pode aumentar temporariamente no relatório, já que os cookies de visitantes estão definidos para serem enviados ao novo local.

## Servidor de rastreamento no Adobe Experience Platform Launch

Servidor de rastreamento é um campo sob a opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] no Adobe Analytics.
4. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Servidor de rastreamento].

Se esse campo ficar em branco, o padrão será `[rsid].112.2o7.net`.

## s.trackingServer no AppMeasurement e no editor de código personalizado do Launch

A varável `s.trackingServer` é uma string que contém o local para o envio de dados.

>[!TIP]
>
>Algumas implementações apontam os dados para `2o7.net`. Embora esse seja um domínio válido para coleta de dados, ele não usa coleta de dados regional. Implementações que usam o `2o7.net` observam tempos de resposta de solicitação de imagem ligeiramente mais rápidos.

## Determine o valor de trackingServer

O valor dessa variável depende do uso de cookies próprios ou de cookies de terceiros. A Adobe recomenda usar cookies próprios na implementação.

### Cookies próprios

Se você usar uma implementação com cookies próprios, é provável que alguém em sua organização já tenha concluído o processo de configuração de cookie próprio. Consulte [Cookies próprios na Experience Cloud](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-first-party.html) no guia do usuário dos serviços principais para obter mais informações sobre o processo de configuração de cookies próprios.

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

Escolha um subdomínio exclusivo da sua organização, um que provavelmente não será escolhido por outra organização que usa o Adobe Analytics.  A namespace de visitante atribuída à sua organização é recomendada.  Verifique se todas as implementações em sua organização usam o mesmo servidor de rastreamento. Pode ser útil manter essas informações em um [documento de design da solução](../../prepare/solution-design.md).

Sua organização pode já estar usando um servidor de rastreamento de terceiros nos domínios `sc.omtrdc.net` ou `2o7.net` .  Eles foram usados principalmente em versões anteriores do Adobe Analytics e ainda são válidos.

>[!NOTE]
>
>Não use subdomínios mais profundos do que `example.data.adobedc.net`. Por exemplo, `custom.example.data.adobedc.net` não é um servidor de rastreamento válido.
