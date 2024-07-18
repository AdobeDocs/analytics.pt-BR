---
title: Visualizações de produto
description: O número de visualizações para páginas de produtos.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 72%

---

# Visualizações de produto

A [métrica](overview.md) de &#39;Exibições de produto&#39; mostra o número de vezes que qualquer produto foi exibido. Essa métrica é útil quando você deseja ver seus produtos mais vistos, ou ver a tendência total das visualizações de produtos ao longo do tempo.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências que correspondem a **qualquer** uma das seguintes opções:

* O valor `prodView` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md); ou
* A variável [`products`](/help/implement/vars/page-vars/products.md) está definida e a variável `events` está vazia.
