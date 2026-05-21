---
title: linkURL
description: Substitua o URL de link gerado automaticamente que o AppMeasurement usa nas chamadas de rastreamento de link.
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
TQID: https://experienceleague.adobe.com/O8Bd28njZQDnffeUwCiNGNSNRHk4FU-z48r4pt7Eths
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 34%

---

# linkURL

Sempre que uma chamada de rastreamento de link é enviada para o Adobe, o AppMeasurement detecta o URL que foi clicado. Este URL ajuda a determinar o tipo de link, como links de download e links de saída. Use a variável `linkURL` para substituir o URL detectado.

Não há dimensões no Analysis Workspace que relatem essa variável. Ele preenche a coluna `page_event_var1` em [Feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md). Se você deseja rastrear o URL de um link clicado, a Adobe recomenda usar uma variável personalizada, como uma [Prop](../page-vars/prop.md). O uso do [Activity Map](/help/analyze/activity-map/overview.md) pode ajudar a simplificar a coleta de dados para links clicados.

## Vincular URL usando o Web SDK

O URL do link é mapeado para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` ou `data.__adobe.analytics.pev1`

## Vincular URL usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.linkURL no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.linkURL` é uma cadeia de caracteres, que contém a URL completa do link clicado. Essa variável não preenche nenhuma dimensão disponível no relatório.

```js
s.linkURL = "https://example.com";
```

Se o terceiro argumento do método [tl()](../functions/tl-method.md) não estiver definido, a variável `linkURL` será usada.
