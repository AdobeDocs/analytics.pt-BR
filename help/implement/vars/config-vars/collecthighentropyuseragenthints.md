---
title: collectHighEntropyUserAgentHint
description: Use a variável collectHighEntropyUserAgentHint para determinar se o Adobe solicitará dicas de alta entropia de navegadores Chromium (por exemplo, Google Chrome e Microsoft Edge).
source-git-commit: 9c386dd26e31b8b2dc2b4a52ae502f9505ec467d
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 3%

---


# collectHighEntropyUserAgentHint

Dicas de cliente de alta entropia são usadas pelo Adobe Analytics para melhorar a identificação do dispositivo e do navegador. Leia mais sobre as dicas do cliente em [esta visão geral e perguntas frequentes](/help/technotes/client-hints.md) bem como [Blog Google](https://web.dev/user-agent-client-hints/).

## Coletar dicas de alta entropia usando o SDK da Web

Dicas de cliente de alta entropia fazem parte das categorias de contexto no SDK da Web. Consulte [Configurar o SDK da Web da plataforma](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) para obter mais detalhes.

## Colete dicas de alta entropia usando a Extensão do Adobe Analytics

**[!UICONTROL Coletar dicas de agente do usuário de alta entropia]** é uma caixa de seleção na opção Geral ao configurar a extensão do Adobe Analytics.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/#/@adobepm/data-collection) usando suas credenciais da Adobe ID.

1. Clique no [!UICONTROL propriedade de tag].

1. Vá para o [!UICONTROL Extensões] e, em seguida, clique em [!UICONTROL Configurar] em Adobe Analytics.

1. Expanda o [!UICONTROL Geral] , que revela o [!UICONTROL Coletar dicas de agente do usuário de alta entropia] caixa de seleção. Ela está desmarcada por padrão.

## collectHighEntropyUserAgentHint no AppMeasurement

O `s.collectHighEntropyUserAgentHints` determina se o AppMeasurement solicita dicas de alta entropia de navegadores Chromium (por exemplo, Google Chrome e Microsoft Edge). Essas dicas são usadas pelo Adobe Analytics para melhorar a identificação do dispositivo e do navegador.

Se definido como TRUE, todas as dicas de alta entropia serão solicitadas do navegador.

`s.collectHighEntropyUserAgentHints = TRUE`

`s.collectHighEntropyUserAgentHints = FALSE`