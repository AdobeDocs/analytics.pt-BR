---
title: campaign
description: Preencha a dimensão “Código de rastreamento”.
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
source-git-commit: e46b15eedda78303e6e29faceea6db8483eee277
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 75%

---

# campaign

A variável `campaign` é dedicada à coleta de códigos de rastreamento no site. Em versões anteriores do Adobe Analytics, ele tinha um tratamento especial, podendo ser usado como um detalhamento na maioria das dimensões. Na versão atual do Adobe Analytics, ela age de forma idêntica a uma eVar.

Essa variável preenche o [Código de rastreamento](/help/components/dimensions/tracking-code.md) dimensão. Normalmente, ele obtém o valor de uma sequência de consulta usando o [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) método de utilitário. No entanto, sua organização determina exatamente como definir essa variável.

## Campaign usando o SDK da Web

A campanha está [mapeado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=pt-BR) no campo XDM `marketing.trackingCode`.

## Campanha usando a extensão do Adobe Analytics

Você pode definir a campanha ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Campanha].

Você pode definir a campanha como um valor ou parâmetro do tipo string.

## s.campaign no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.campaign` é uma string que geralmente contém um código de rastreamento usado em esforços de marketing. Seu comprimento máximo é de 255 bytes; valores com mais de 255 bytes são truncados automaticamente quando enviados para a Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
