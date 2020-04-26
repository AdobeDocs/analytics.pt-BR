---
title: trackDownloadLinks
description: Ative ou desative o rastreamento automático de links para links de download.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackDownLoadLinks

Adobe offers the ability to track download links without manually setting the [`tl()`](../functions/tl-method.md) method for each download link. Ative essa variável se desejar usar o rastreamento automático de links para links de download.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com os valores em [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Se houver uma correspondência, uma chamada de rastreamento de link de download será acionada automaticamente.

## Rastrear links de download no Adobe Experience Platform Launch

Rastrear links de download é uma caixa de seleção na opção [!UICONTROL Rastreamento de link] que aparece ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Rastrear links de download].

Clique na caixa de seleção para ativar o rastreamento automático de link de download.

## s.trackDownloadLinks no AppMeasurement e editor de código personalizado do Launch

`s.trackDownloadLinks` é uma variável do tipo booleano que ativa ou desativa o rastreamento automático de link de download. If you do not want to track download links, or would prefer to manually call the `tl()` method to track downloads, set this variable to `false`.

```js
s.trackDownloadLinks = true;
```
