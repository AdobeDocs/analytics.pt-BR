---
title: trackDownloadLinks
description: Ative ou desative o rastreamento automático de link para links de download.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackDownLoadLinks

A Adobe oferece a capacidade de rastrear links de download sem definir manualmente o [`tl()`](../functions/tl-method.md) método para cada link de download. Ative essa variável se desejar usar o rastreamento automático de link para links de download.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com valores em [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Se houver uma correspondência, uma chamada de rastreamento de link de download será automaticamente acionada.

## Rastrear links de download no Adobe Experience Platform Launch

Rastrear links de download é uma caixa de seleção sob o [!UICONTROL Link Tracking] acordeão ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão em Adobe Analytics.
4. Expanda o [!UICONTROL Link Tracking] acordeão, que revela a [!UICONTROL Track download links] caixa de seleção.

Clique na caixa de seleção para ativar o rastreamento automático de link de download.

## s.trackDownloadLinks no AppMeasurement e no editor de código personalizado Iniciar

O `s.trackDownloadLinks` é um booliano que ativa ou desativa o rastreamento automático de link de download. Se você não quiser rastrear links de download, ou preferir chamar manualmente o `tl()` método para rastrear downloads, defina essa variável como `false`.

```js
s.trackDownloadLinks = true;
```
