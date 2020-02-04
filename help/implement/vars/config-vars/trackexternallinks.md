---
title: trackExternalLinks
description: Ative ou desative o rastreamento automático de link para links de saída.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackExternalLinks

A Adobe oferece a capacidade de rastrear links externos sem definir manualmente a `tl()` função para cada link de saída. Ative essa variável se desejar usar o rastreamento automático de link para links de saída.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com valores em `linkInternalFilters` e `linkExternalFilters`. Se houver uma correspondência, uma chamada de rastreamento de link de saída será acionada automaticamente.

## Rastrear links externos no Adobe Experience Platform Launch

Rastrear links externos é uma caixa de seleção na opção Rastreamento [!UICONTROL de] links ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda a opção Rastreamento [!UICONTROL de] link, que revela a caixa de seleção Rastrear links  de saída.

Clique na caixa de seleção para ativar o rastreamento automático de link de saída.

## s.trackExternalLinks no AppMeasurement e no editor de código personalizado Iniciar

O `s.trackExternalLinks` é um booliano que ativa ou desativa o rastreamento automático de link de saída. Se você não quiser rastrear links externos, ou preferir chamar manualmente a `tl()` função para rastrear links de saída, defina essa variável como `false`.

```js
s.trackDownloadLinks = true;
```
