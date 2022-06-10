---
title: trackExternalLinks
description: Ative ou desative o rastreamento automático de links para links de saída.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 52%

---

# trackExternalLinks

A Adobe oferece a capacidade de rastrear links externos sem definir manualmente o método [`tl()`](../functions/tl-method.md) para cada link de saída. Ative essa variável se desejar usar o rastreamento automático de links para links de saída.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com valores em [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). Se houver uma correspondência, uma chamada de rastreamento de link de saída será acionada automaticamente.

## Ativar ou desativar a coleção de cliques usando a extensão Web SDK

Use o [!UICONTROL Ativar coleta de dados de clique] ao configurar o SDK da Web. Essa caixa de seleção manipula os links de saída e de download.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para o [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** botão abaixo [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleta de dados], clique no botão **[!UICONTROL Ativar coleta de dados de clique]** caixa de seleção.

## Ative ou desative a coleta de cliques manualmente implementando o SDK da Web

Configurar o SDK usando [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). O campo é um booleano que determina se os dados associados aos cliques em links são coletados automaticamente. O valor padrão é `true`. Defina esse valor como `false` se desejar desativar o rastreamento automático de links. Essa configuração lida com o rastreamento automático de links para links de download e de saída.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Rastrear links externos usando a extensão Adobe Analytics

Rastrear links externos é uma caixa de seleção na opção [!UICONTROL Rastreamento de links] ao configurar a extensão do Adobe Analytics.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Rastrear links externos].

Clique na caixa de seleção para ativar o rastreamento automático de links de saída.

## s.trackExternalLinks no AppMeasurement e no editor de código personalizado da extensão do Analytics

`s.trackExternalLinks` é uma variável do tipo booleano que ativa ou desativa o rastreamento automático de links de saída. Se você não quiser rastrear links externos, ou se preferir chamar manualmente o método `tl()` para rastrear links de saída, defina essa variável como `false`.

```js
s.trackExternalLinks = true;
```
