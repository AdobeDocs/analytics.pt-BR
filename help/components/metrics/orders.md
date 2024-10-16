---
title: Pedidos
description: O número de compras feitas.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: a1fbd3f483d3a236fe5dc3246f5e90c1b3f51ba9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 65%

---

# Pedidos

A [métrica](overview.md) de &quot;Pedidos&quot; mostra o número total de eventos de compra feitos em seu site. Essa métrica é essencial para sites de comércio eletrônico na medição da conversão. É possível combinar essa métrica com qualquer dimensão para ver quais itens de dimensão contribuíram para um pedido. Por exemplo, você pode ver as campanhas principais (usando a dimensão [Código de rastreamento](../dimensions/tracking-code.md)) ou os termos de pesquisa internos principais (usando uma [eVar](../dimensions/evar.md)) que contribuíram com as compras.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências em que `purchase` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md).
