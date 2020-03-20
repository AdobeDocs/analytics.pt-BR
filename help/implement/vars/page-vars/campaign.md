---
title: campaign
description: Preencha a dimensão “Código de rastreamento”.
translation-type: tm+mt
source-git-commit: 7220b99268532adb2e425d52744dbc3efb615953

---


# campaign

A variável `campaign` é dedicada à coleta de códigos de rastreamento no site. Em versões anteriores do Adobe Analytics, ele tinha um tratamento especial, podendo ser usado como um detalhamento na maioria das dimensões. Na versão atual do Adobe Analytics, ela age de forma idêntica a uma eVar.

Essa variável preenche a dimensão &quot;Código de rastreamento&quot;.

## Campanha no Adobe Experience Platform Launch

Você pode definir a campanha ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Em [!UICONTROL Actions], clique em uma [!UICONTROL Adobe Analytics - Set Variables] ação existente ou no ícone &#39;+&#39;.
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Campaign] section.

Você pode definir a campanha como um valor ou parâmetro do tipo string.

## s.campaign no AppMeasurement e no editor de código personalizado do Launch

A variável `s.campaign` é uma string que geralmente contém um código de rastreamento usado em esforços de marketing. Seu comprimento máximo é de 255 bytes; valores com mais de 255 bytes são truncados automaticamente quando enviados para a Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
