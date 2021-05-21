---
title: trackDownloadLinks
description: Ative ou desative o rastreamento automático de links para links de download.
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '183'
ht-degree: 100%

---

# trackDownLoadLinks

A Adobe oferece a capacidade de rastrear links de download sem definir manualmente o método [`tl()`](../functions/tl-method.md) para cada link de download. Ative essa variável se desejar usar o rastreamento automático de links para links de download.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com os valores em [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Se houver uma correspondência, uma chamada de rastreamento de link de download será acionada automaticamente.

## Rastrear links de download no Adobe Experience Platform Launch

Rastrear links de download é uma caixa de seleção na opção [!UICONTROL Rastreamento de link] que aparece ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Rastrear links de download].

Clique na caixa de seleção para ativar o rastreamento automático de link de download.

## s.trackDownloadLinks no AppMeasurement e editor de código personalizado do Launch

`s.trackDownloadLinks` é uma variável do tipo booleano que ativa ou desativa o rastreamento automático de link de download. Se você não quiser rastrear links de download, ou se preferir chamar manualmente o método `tl()` para rastrear downloads, defina essa variável como `false`.

```js
s.trackDownloadLinks = true;
```
