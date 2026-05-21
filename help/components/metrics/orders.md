---
title: Pedidos
description: O número de compras feitas.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
TQID: https://experienceleague.adobe.com/jRd-oUTfcJXACj-mkEyzRm8k-rxcVCxe7U3lROIy7DQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 90
ht-degree: 65%

---

# Pedidos

A [métrica](overview.md) de &quot;Pedidos&quot; mostra o número total de eventos de compra feitos em seu site. Essa métrica é essencial para sites de comércio eletrônico na medição da conversão. É possível combinar essa métrica com qualquer dimensão para ver quais itens de dimensão contribuíram para um pedido. Por exemplo, você pode ver as campanhas principais (usando a dimensão [Código de rastreamento](../dimensions/tracking-code.md)) ou os termos de pesquisa internos principais (usando uma [eVar](../dimensions/evar.md)) que contribuíram com as compras.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências em que `purchase` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md).
