---
title: collectHighEntropyUserAgentHints
description: Use a variável collectHighEntropyUserAgentHints para determinar se a Adobe solicitará dicas de alta entropia de navegadores Chromium (por exemplo, Google Chrome e Microsoft Edge).
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: https://experienceleague.adobe.com/jipxox--J6tVTjpES3YuOTOqL-SXvCMLSvvbpj620Q4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 100%

---

# collectHighEntropyUserAgentHints

Dicas de cliente de alta entropia são usadas pelo Adobe Analytics para melhorar a identificação do dispositivo e do navegador. Essa opção está disponível a partir da versão 2.23.0 do AppMeasurement.js. Leia mais sobre as dicas do cliente [nesta visão geral e perguntas frequentes](/help/technotes/client-hints.md) e no [blog do Google](https://web.dev/user-agent-client-hints/).

## Colete dicas de alta entropia usando o SDK da Web

Dicas de cliente de alta entropia fazem parte das categorias de contexto no SDK da Web. Consulte [Configurar o SDK da Web da plataforma](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) para obter mais detalhes.

## Colete dicas de alta entropia usando a extensão do Adobe Analytics

**[!UICONTROL Coletar dicas de agente do usuário de alta entropia]** é uma caixa de seleção na opção Geral ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/#/@adobepm/data-collection) usando suas credenciais da Adobe ID.
1. Clique na [!UICONTROL propriedade de tag] desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] no Adobe Analytics.
1. Expanda a opção [!UICONTROL Geral], que revela a caixa de seleção [!UICONTROL Coletar dicas de agente do usuário de alta entropia]. Ela está desmarcada por padrão.

## collectHighEntropyUserAgentHints no AppMeasurement

A variável `s.collectHighEntropyUserAgentHints` determina se o AppMeasurement solicita dicas de alta entropia de navegadores Chromium (por exemplo, Google Chrome ou Microsoft Edge). Essas dicas são usadas pelo Adobe Analytics para melhorar a identificação do dispositivo e do navegador.

Se definido como `true`, todas as dicas de alta entropia serão solicitadas do navegador.

```js
s.collectHighEntropyUserAgentHints = true;
```
