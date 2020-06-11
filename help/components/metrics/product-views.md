---
title: visualizações de produtos
description: O número de visualizações para páginas de produtos.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---


# visualizações de produtos

A métrica &#39;visualizações de produto&#39; mostra o número de vezes que qualquer produto foi exibido. Essa métrica é útil quando você deseja ver seus produtos mais vistos, ou ver a tendência total das visualizações de produtos ao longo do tempo.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências que correspondem a **qualquer** uma das seguintes opções:

* O valor `prodView` existe na [`events`](/help/implement/vars/page-vars/events/events-overview.md) variável; ou
* A [`products`](/help/implement/vars/page-vars/products.md) variável está definida e nenhum evento de carrinho de compras existe na `events` variável. Qualquer evento que não seja personalizado (`event1` - `event1000`) é um evento de carrinho de compras.