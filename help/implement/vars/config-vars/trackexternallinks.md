---
title: trackExternalLinks
description: Ative ou desative o rastreamento automático de links para links de saída.
feature: Appmeasurement Implementation
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 60%

---

# trackExternalLinks

A Adobe oferece a capacidade de rastrear links externos sem definir manualmente o método [`tl()`](../functions/tl-method.md) para cada link de saída. Ative essa variável se desejar usar o rastreamento automático de links para links de saída.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com valores em [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). Se houver uma correspondência, uma chamada de rastreamento de link de saída será acionada automaticamente.

## Ativar ou desativar a coleção de cliques usando a extensão Web SDK

Use a caixa de seleção [!UICONTROL Habilitar coleta de dados de cliques] ao configurar o Web SDK. Essa caixa de seleção lida com links de saída e de download.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** em [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleção de dados], clique na caixa de seleção **[!UICONTROL Habilitar e clicar na coleção de dados]**.

## Ativar ou desativar a coleção de cliques que implementa manualmente o Web SDK

Configurar o SDK usando [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR#clickCollectionEnabled). O campo é do tipo booleano e determina se os dados associados aos cliques em links são coletados automaticamente. O valor padrão é `true`. Defina esse valor como `false` se desejar desabilitar o rastreamento automático de links. Essa configuração lida com o rastreamento automático de links para links de download e de saída.

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Rastrear links externos usando a extensão do Adobe Analytics

Rastrear links externos é uma caixa de seleção na opção [!UICONTROL Rastreamento de links] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Rastrear links externos].

Clique na caixa de seleção para ativar o rastreamento automático de links de saída.

## s.trackExternalLinks no AppMeasurement e no editor de código personalizado da extensão do Analytics

`s.trackExternalLinks` é uma variável do tipo booleano que ativa ou desativa o rastreamento automático de links de saída. Se você não quiser rastrear links externos, ou se preferir chamar manualmente o método `tl()` para rastrear links de saída, defina essa variável como `false`.

```js
s.trackExternalLinks = true;
```
