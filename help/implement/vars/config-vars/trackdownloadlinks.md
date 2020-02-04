---
title: trackDownloadLinks
description: Ative ou desative o rastreamento automático de link para links de download.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackDownLoadLinks

A Adobe oferece a capacidade de rastrear links de download sem definir manualmente a `tl()` função para cada link de download. Ative essa variável se desejar usar o rastreamento automático de link para links de download.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com valores em `downloadLinkFileTypes`. Se houver uma correspondência, uma chamada de rastreamento de link de download será automaticamente acionada.

## Rastrear links de download no Adobe Experience Platform Launch

Rastrear links de download é uma caixa de seleção na opção Rastreamento [!UICONTROL de] link ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda a opção Rastreamento [!UICONTROL de] link, que revela a caixa de seleção [!UICONTROL Rastrear links] de download.

Clique na caixa de seleção para ativar o rastreamento automático de link de download.

## s.trackDownloadLinks no AppMeasurement e no editor de código personalizado Iniciar

O `s.trackDownloadLinks` é um booliano que ativa ou desativa o rastreamento automático de link de download. Se você não quiser rastrear links de download, ou preferir chamar manualmente a `tl()` função para rastrear downloads, defina essa variável como `false`.

```js
s.trackDownloadLinks = true;
```
