---
title: trackDownloadLinks
description: Habilite ou desabilite o rastreamento automático de links para links de download.
feature: Appmeasurement Implementation
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/mH9olBbVVqz9WCBCWiZuDe9JcljL0ADOesKSfEE6gkA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 352
ht-degree: 49%

---

# trackDownloadLinks

A Adobe oferece a capacidade de rastrear links de download sem definir manualmente o método [`tl()`](../functions/tl-method.md) para cada link de download. Habilite essa variável se desejar usar o rastreamento automático de links para links de download.

Quando habilitado, o AppMeasurement compara qualquer URL de link clicado com os valores em [`linkDownloadFileTypes`](linkdownloadfiletypes.md). Se houver uma correspondência, uma chamada de rastreamento de link de download será acionada automaticamente.

## Ativar ou desativar a coleção de cliques usando a extensão Web SDK

Use a caixa de seleção [!UICONTROL Habilitar coleta de dados de cliques] ao configurar o Web SDK. Essa caixa de seleção lida com links de saída e de download.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
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

Clique na caixa de seleção para habilitar o rastreamento automático de link de download.

## s.trackDownloadLinks no AppMeasurement e no editor de código personalizado da extensão do Analytics

`s.trackDownloadLinks` é uma variável do tipo booleano que habilita ou desabilita o rastreamento automático de link de download. Se você não quiser rastrear links de download, ou se preferir chamar manualmente o método `tl()` para rastrear downloads, defina essa variável como `false`. A variável [linkDownloadFileTypes](linkdownloadfiletypes.md) também deve ser definida para que o rastreamento automático de link de download funcione.

```js
s.trackDownloadLinks = true;
```
