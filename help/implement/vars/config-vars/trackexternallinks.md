---
title: trackExternalLinks
description: Ative ou desative o rastreamento automático de links para links de saída.
translation-type: tm+mt
source-git-commit: 94218548dc4e3efd57df95c992003e94640e4330

---


# trackExternalLinks

Adobe offers the ability to track outbound links without manually setting the [`tl()`](../functions/tl-method.md) method for each exit link. Ative essa variável se desejar usar o rastreamento automático de links para links de saída.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com valores em [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). Se houver uma correspondência, uma chamada de rastreamento de link de saída será acionada automaticamente.

## Rastrear links externos no Adobe Experience Platform Launch

Track outbound links is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expanda o [!UICONTROL Link Tracking] acordeão, que revela a [!UICONTROL Track outbound links] caixa de seleção.

Clique na caixa de seleção para ativar o rastreamento automático de links de saída.

## s.trackExternalLinks no AppMeasurement e no editor de código personalizado do Launch

`s.trackExternalLinks` é uma variável do tipo booleano que ativa ou desativa o rastreamento automático de links de saída. If you do not want to track outbound links, or would prefer to manually call the `tl()` method to track exit links, set this variable to `false`.

```js
s.trackExternalLinks = true;
```
