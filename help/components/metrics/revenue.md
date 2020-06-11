---
title: Receita
description: A quantidade monetária de produtos comprados em todos os pedidos.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---


# Receita

A métrica &#39;Receita&#39; mostra a quantidade monetária de produtos comprados em todos os pedidos. Essa métrica é vital para sites de comércio eletrônico na medição da conversão. É possível combinar essa métrica com qualquer dimensão para ver quais valores de dimensão contribuíram para a receita. Por exemplo, você pode ver as campanhas principais (usando a dimensão do código [de](../dimensions/tracking-code.md) rastreamento) ou os termos de pesquisa internos principais (usando uma [eVar](../dimensions/evar.md)).

## Como essa métrica é calculada

Para cada ocorrência em que `purchase` existe na [`events`](/help/implement/vars/page-vars/events/event-purchase.md) variável, soma o campo &#39;Preço&#39; dentro da [`products`](/help/implement/vars/page-vars/products.md) variável.

Essa métrica depende da variável [currencyCode](/help/implement/vars/config-vars/currencycode.md) se a moeda na página for diferente da moeda nativa do conjunto de relatórios.
