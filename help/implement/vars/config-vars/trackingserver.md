---
title: trackingServer
description: Defina para que local as solicitações de imagens são enviadas.
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 284f121428ce9d682b42309dd85cfd117285a7e5
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 52%

---

# trackingServer

A Adobe coleta dados em seu site recebendo uma solicitação de imagem gerada pelo visitante. A variável `trackingServer` determina para que local uma solicitação de imagem é enviada. Se essa variável não estiver definida corretamente, sua implementação pode sofrer perda de dados.

>[!WARNING]
>
>Alterar esse valor faz com que o AppMeasurement procure cookies em um local diferente. A contagem de visitantes únicos pode aumentar temporariamente no relatório, já que os cookies de visitantes estão definidos para serem enviados ao novo local.

## Domínio do Edge usando a extensão SDK da Web

O SDK da Web usa o [!UICONTROL domínio do Edge] para manipular o Servidor de Rastreamento e o Servidor de Rastreamento Seguro. Você pode definir o valor desejado do [!UICONTROL domínio do Edge] ao configurar a extensão SDK da Web.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** em [!UICONTROL Adobe Experience Platform Web SDK].
1. Defina o campo de texto desejado **[!UICONTROL domínio Edge]**.

Consulte [Configurar a extensão do SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=pt-BR) na documentação do SDK da Web para obter mais informações.

>[!TIP]
>
>Se sua organização mudar para o SDK da Web de uma implementação de extensão do AppMeasurement ou do Analytics, esse campo poderá usar o mesmo valor contido em `trackingServerSecure` (ou `trackingServer`).

## Domínio Edge que implementa manualmente o SDK da Web

Configurar o SDK usando [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR). O campo é uma cadeia de caracteres que determina o domínio para o qual enviar dados.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Servidor de rastreamento usando a extensão do Adobe Analytics

Servidor de rastreamento é um campo sob a opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Servidor de rastreamento].

Se esse campo ficar em branco, o padrão será `[rsid].data.adobedc.net`.

## s.trackingServer no AppMeasurement e o editor de código personalizado da extensão do Analytics

A varável `s.trackingServer` é uma string que contém o local para o envio de dados.

## Considerações para determinar o valor de `trackingServer`

Você pode optar por usar domínios de servidor de rastreamento do Adobe (por exemplo, `adobedc.net`) ou pode passar por um processo especial para configurar um servidor de rastreamento que corresponda ao domínio dos sites (por exemplo, `data.mydomain.com`), também conhecido como implementação CNAME. Ter um servidor de rastreamento que corresponda ao domínio do site pode ter alguns benefícios, dependendo de outros aspectos da implementação. Quando o servidor de rastreamento não corresponde ao domínio da página atual, os cookies definidos pelo AppMeasurement devem ser definidos como de terceiros. Se o navegador não for compatível com cookies de terceiros, essa incompatibilidade poderá interferir em determinadas funcionalidades do Analytics:

- Definição de identificadores: se estiver usando o Serviço de identidade do Experience Cloud, o servidor de rastreamento não terá impacto sobre a definição de cookies. No entanto, se você estiver usando identificadores herdados do Analytics (também conhecido como cookie `s_vi`) e o servidor de coleção não corresponder ao domínio atual, os cookies deverão ser definidos como de terceiros. Nesse caso, se cookies de terceiros forem bloqueados pelo navegador, o Analytics definirá um id de fallback primário (`s_fid`) em vez do cookie `s_vi` padrão.
- O rastreamento de links não funcionará para links internos.
- O Activity Map não funcionará para links internos.
- Verificação de cookies.

### Cookies próprios

Se você usar uma implementação com cookies próprios, é provável que alguém em sua organização já tenha concluído o processo de configuração de cookie próprio. Consulte [Cookies próprios na Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=pt-BR) no guia do usuário dos serviços principais para obter mais informações sobre o processo de configuração de cookies próprios.

O indivíduo que configura inicialmente a implementação do cookie próprio também define o domínio e o subdomínio que são usados. Por exemplo:

```js
s.trackingServer = "data.example.com";
```

### Servidor de rastreamento de terceiros

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
