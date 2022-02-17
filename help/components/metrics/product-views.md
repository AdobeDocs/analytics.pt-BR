---
title: Visualizações de produto
description: O número de visualizações para páginas de produtos.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 100%

---

# Visualizações de produto

A métrica “Visualizações de produto” mostra o número de vezes que um produto foi exibido. Essa métrica é útil quando você deseja ver seus produtos mais vistos, ou ver a tendência total das visualizações de produtos ao longo do tempo.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências que correspondem a **qualquer** uma das seguintes opções:

* O valor `prodView` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md); ou
* A variável [`products`](/help/implement/vars/page-vars/products.md) está definida e nenhum evento de carrinho de compras existe na variável `events`. Qualquer evento que não seja personalizado (`event1` - `event1000`) é um evento de carrinho de compras.
