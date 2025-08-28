---
title: trackDownloadLinks
description: Ative ou desative o rastreamento automático de links para links de download.
feature: Appmeasurement Implementation
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
role: Admin, Developer
source-git-commit: 7176e068dd05c5589d741f3194d2ad5d795e017d
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 50%

---

# trackDownloadLinks

A Adobe oferece a capacidade de rastrear links de download sem definir manualmente o método [`tl()`](../functions/tl-method.md) para cada link de download. Ative essa variável se desejar usar o rastreamento automático de links para links de download.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com os valores em [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Se houver uma correspondência, uma chamada de rastreamento de link de download será acionada automaticamente.

## Ativar ou desativar a coleção de cliques usando a extensão Web SDK

Use a caixa de seleção [!UICONTROL Habilitar coleta de dados de cliques] ao configurar o Web SDK. Essa caixa de seleção lida com links de saída e de download.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** em [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleção de dados], clique na caixa de seleção **[!UICONTROL Habilitar e clicar na coleção de dados]**.

## Ativar ou desativar a coleção de cliques que implementa manualmente o Web SDK

Configurar o SDK usando [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). O campo é do tipo booleano e determina se os dados associados aos cliques em links são coletados automaticamente. O valor padrão é `true`. Defina esse valor como `false` se desejar desabilitar o rastreamento automático de links. Essa configuração lida com o rastreamento automático de links para links de download e de saída.

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

`s.trackDownloadLinks` é uma variável do tipo booleano que ativa ou desativa o rastreamento automático de link de download. Se você não quiser rastrear links de download, ou se preferir chamar manualmente o método `tl()` para rastrear downloads, defina essa variável como `false`. A variável [linkDownloadFileTypes](linkdownloadfiletypes.md) também deve ser definida para que o rastreamento automático de link de download funcione.

```js
s.trackDownloadLinks = true;
```
