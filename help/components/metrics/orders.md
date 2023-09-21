---
title: Pedidos
description: O número de compras feitas.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 84%

---

# Pedidos

Os &quot;Pedidos&quot; [métrica](overview.md) mostra o número total de eventos de compra feitos em seu site. Essa métrica é essencial para sites de comércio eletrônico na medição da conversão. É possível combinar essa métrica com qualquer dimensão para ver quais itens de dimensão contribuíram para um pedido. Por exemplo, você pode ver as campanhas principais (usando a dimensão [Código de rastreamento](../dimensions/tracking-code.md)) ou os termos de pesquisa internos principais (usando uma [eVar](../dimensions/evar.md)) que contribuíram com as compras.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências em que `purchase` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md).
