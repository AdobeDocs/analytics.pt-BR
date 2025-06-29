---
title: campaign
description: Preencha a dimensão “Código de rastreamento”.
feature: Appmeasurement Implementation
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 67%

---

# campaign

A variável `campaign` é dedicada à coleta de códigos de rastreamento no site. Em versões anteriores do Adobe Analytics, ele tinha um tratamento especial, podendo ser usado como um detalhamento na maioria das dimensões. Na versão atual do Adobe Analytics, ela age de forma idêntica a uma eVar.

Esta variável preenche a dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md). Normalmente, o valor é obtido de uma cadeia de caracteres de consulta usando o método de utilitário [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md). No entanto, sua organização determina exatamente como definir essa variável.

## Campaign usando a Web SDK

O Campaign é mapeado para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `marketing.trackingCode`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.campaign` ou `data.__adobe.analytics.v0`

## Campanha usando a extensão do Adobe Analytics

Você pode definir a campanha ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de Ação] como [!UICONTROL Definir Variáveis].
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
