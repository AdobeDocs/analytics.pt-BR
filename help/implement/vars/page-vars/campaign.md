---
title: campaign
description: Preencha a dimensão “Código de rastreamento”.
translation-type: ht
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# campaign

A variável `campaign` é dedicada à coleta de códigos de rastreamento no site. Em versões anteriores do Adobe Analytics, ele tinha um tratamento especial, podendo ser usado como um detalhamento na maioria das dimensões. Na versão atual do Adobe Analytics, ela age de forma idêntica a uma eVar.

Essa variável preenche a dimensão &quot;Código de rastreamento&quot;.

## Campanha no Adobe Experience Platform Launch

Você pode definir a campanha ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Campanha].

Você pode definir a campanha como um valor ou parâmetro do tipo string.

## s.campaign no AppMeasurement e no editor de código personalizado do Launch

A variável `s.campaign` é uma string que geralmente contém um código de rastreamento usado em esforços de marketing. Seu comprimento máximo é de 255 bytes; valores com mais de 100 bytes são truncados automaticamente quando enviados para a Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
