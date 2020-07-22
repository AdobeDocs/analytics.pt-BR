---
title: Pedidos
description: O número de compras feitas.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 2%

---


# Pedidos

A métrica &quot;Pedidos&quot; mostra o número total de eventos de compra feitos em seu site. Essa métrica é vital para sites de comércio eletrônico na medição da conversão. É possível combinar essa métrica com qualquer dimensão para ver quais itens de dimensão contribuíram para um pedido. Por exemplo, você pode ver as campanhas principais (usando a dimensão do código [de](../dimensions/tracking-code.md) rastreamento) ou os termos de pesquisa internos principais (usando uma [eVar](../dimensions/evar.md)) que contribuíram com as compras.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências em que `purchase` existe na [`events`](/help/implement/vars/page-vars/events/events-overview.md) variável.
