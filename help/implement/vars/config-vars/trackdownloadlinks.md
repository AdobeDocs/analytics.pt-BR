---
title: trackDownloadLinks
description: Ative ou desative o rastreamento automático de links para links de download.
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 59%

---

# trackDownLoadLinks

A Adobe oferece a capacidade de rastrear links de download sem definir manualmente o método [`tl()`](../functions/tl-method.md) para cada link de download. Ative essa variável se desejar usar o rastreamento automático de links para links de download.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com os valores em [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Se houver uma correspondência, uma chamada de rastreamento de link de download será acionada automaticamente.

## Ativar ou desativar a coleção de cliques usando a extensão SDK da Web

Use o [!UICONTROL Ativar a coleta de dados de cliques] caixa de seleção ao configurar o SDK da Web. Essa caixa de seleção lida com links de saída e de download.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a [!UICONTROL Extensões] e clique na guia **[!UICONTROL Configurar]** botão em [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleta de dados], clique no link **[!UICONTROL Ativar a coleta de dados de cliques]** caixa de seleção

## Ativar ou desativar a coleção de cliques que implementa manualmente o SDK da Web

Configurar o SDK usando o [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). O campo é do tipo booleano e determina se os dados associados aos cliques em links são coletados automaticamente. O valor padrão é `true`. Defina esse valor como `false` se quiser desativar o rastreamento automático de links. Essa configuração lida com o rastreamento automático de links para links de download e de saída.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Rastrear links de download usando a extensão do Adobe Analytics

Rastrear links de download é uma caixa de seleção na opção [!UICONTROL Rastreamento de link] que aparece ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Rastrear links de download].

Clique na caixa de seleção para ativar o rastreamento automático de link de download.

## s.trackDownloadLinks no AppMeasurement e no editor de código personalizado da extensão do Analytics

`s.trackDownloadLinks` é uma variável do tipo booleano que ativa ou desativa o rastreamento automático de link de download. Se você não quiser rastrear links de download, ou se preferir chamar manualmente o método `tl()` para rastrear downloads, defina essa variável como `false`.

```js
s.trackDownloadLinks = true;
```
