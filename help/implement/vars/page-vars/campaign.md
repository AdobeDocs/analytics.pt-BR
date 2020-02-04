---
title: campaign
description: Preencha a dimensão 'Código de rastreamento'.
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# campaign

A `campaign` variável é dedicada à coleta de códigos de rastreamento no site. Em versões anteriores do Adobe Analytics, ele tinha um tratamento especial onde poderia ser usado como um detalhamento para a maioria das dimensões. Na versão atual do Adobe Analytics, ele age de forma idêntica a uma eVar.

Essa variável preenche a dimensão &quot;Código de rastreamento&quot;.

## Campaign na Adobe Experience Platform Launch

Você pode definir a campanha ao configurar a extensão do Analytics (variáveis globais) ou as regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Campanha] .

Você pode definir a campanha como um valor ou parâmetro de sequência de consulta.

## s.campaign no AppMeasurement e no editor de código personalizado Iniciar

A `s.campaign` variável é uma string que geralmente contém um código de rastreamento usado em esforços de marketing. Seu comprimento máximo é de 255 bytes; valores com mais de 100 bytes são truncados automaticamente quando enviados para a Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
