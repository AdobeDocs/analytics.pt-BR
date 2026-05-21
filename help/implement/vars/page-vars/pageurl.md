---
title: pageURL
description: Substitua o URL da página coletado automaticamente em seu site.
feature: Appmeasurement Implementation
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
role: Admin, Developer
TQID: https://experienceleague.adobe.com/DZM2tZlfVX0g9OYMj6tPFuHInBZdBrboJ4vGz16Lfrs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 84%

---

# pageURL

O AppMeasurement coleta automaticamente o URL da página em cada ocorrência. Se você quiser substituir o URL da página coletado automaticamente pelo AppMeasurement, use essa variável. Não é necessário definir essa variável na maioria dos casos.

>[!NOTE]
>
>Essa variável não é uma dimensão disponível no Analysis Workspace. Ela só está disponível no Data Warehouse e nos Feeds de dados. Além disso, os servidores de coleção de dados da Adobe removem essa dimensão de todas as solicitações de imagem de [rastreamento de link](/help/implement/vars/functions/tl-method.md). Se você quiser usar o URL da página como uma dimensão no Analysis Workspace ou quiser essa dimensão em ocorrências de rastreamento de link, considere transmitir a variável `pageURL` para uma [eVar](evar.md) em cada ocorrência.

## URL da página usando o Web SDK

O URL da página é mapeado para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.URL`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageURL` ou `data.__adobe.analytics.g`

## URL da página usando a extensão do Adobe Analytics

A extensão Analytics da Coleção de dados da Adobe Experience Platform preenche automaticamente o URL da página. No entanto, é possível definir a substituição do URL da página ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia **[!UICONTROL Regras]** e clique na regra desejada (ou crie uma regra).
4. Em **[!UICONTROL Ações]**, clique em uma ação **[!UICONTROL Adobe Analytics - Definir variáveis]** ou clique no ícone “+”.
5. Defina a lista suspensa **[!UICONTROL Extensão]** como Adobe Analytics e o **[!UICONTROL Tipo de ação]** como **[!UICONTROL Definir variáveis]**.
6. Localize a seção **[!UICONTROL URL da página]**.

Você pode definir o URL da página como qualquer valor de string.

## s.pageURL no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.pageURL` é uma string que contém o URL da página. O AppMeasurement coleta essa variável automaticamente, no entanto, você pode substituir o valor dela, se desejar.

```js
s.pageURL = "https://example.com";
```

Se você deseja usar o URL da página como uma dimensão nos relatórios, considere usar o seguinte na implementação:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

Se estiver usando a `digitalData` [camada de dados](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
