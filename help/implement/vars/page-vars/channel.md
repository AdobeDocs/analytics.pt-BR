---
title: canal
description: Preencha a dimensão “Seções do site”.
feature: Appmeasurement Implementation
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/8O57DR-hVZaTuPvVFeOabX-OO6t-Ym7XCKogurcI810'
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
source-wordcount: 198
ht-degree: 83%

---

# canal

A variável `channel` geralmente armazena a seção do site em que uma determinada página está. É útil determinar quais grupos do site são mais populares. Essa variável preenche a dimensão &quot;Seções do site&quot;.

## Canal usando o Web SDK

O canal é mapeado para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `web.webPageDetails.siteSection`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.channel` ou `data.__adobe.analytics.ch`

## Canal usando a extensão do Adobe Analytics

É possível definir um canal ao configurar a extensão do Analytics (variáveis globais) ou sob Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Canal].

Você pode definir um canal como qualquer valor de string ou elemento de dados.

## s.channel no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.channel` é uma string que normalmente contém a seção do site da página. A variável tem um valor máximo de 100 bytes; valores mais longos são truncados.

```js
s.channel = "Example site section";
```

Se estiver usando a `digitalData` [camada de dados](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
