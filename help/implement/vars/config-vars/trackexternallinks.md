---
title: trackExternalLinks
description: Habilite ou desabilite o rastreamento automático de links para links de saída.
feature: Appmeasurement Implementation
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
role: Admin, Developer
TQID: https://experienceleague.adobe.com/jNToCI8XjnbDNdTj6gwveVIWt3Ehue6Hp1HWM789UeI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 340
ht-degree: 59%

---

# trackExternalLinks

A Adobe oferece a capacidade de rastrear links externos sem definir manualmente o método [`tl()`](../functions/tl-method.md) para cada link de saída. Habilite essa variável se desejar usar o rastreamento automático de links para links de saída.

Quando habilitado, o AppMeasurement compara qualquer URL de link clicado com valores em [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). Se houver uma correspondência, uma chamada de rastreamento de link de saída será acionada automaticamente.

## Ativar ou desativar a coleção de cliques usando a extensão Web SDK

Use a caixa de seleção [!UICONTROL Habilitar coleta de dados de cliques] ao configurar o Web SDK. Essa caixa de seleção lida com links de saída e de download.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
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

Clique na caixa de seleção para habilitar o rastreamento automático de links de saída.

## s.trackExternalLinks no AppMeasurement e no editor de código personalizado da extensão do Analytics

`s.trackExternalLinks` é uma variável do tipo booleano que habilita ou desabilita o rastreamento automático de links de saída. Se você não quiser rastrear links externos, ou se preferir chamar manualmente o método `tl()` para rastrear links de saída, defina essa variável como `false`.

```js
s.trackExternalLinks = true;
```
