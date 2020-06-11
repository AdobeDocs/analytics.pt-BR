---
title: Unidades
description: O número total de produtos comprados em todos os pedidos.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---


# Unidades

A métrica &#39;Unidades&#39; mostra o número total de produtos comprados em todos os pedidos. Essa métrica é vital para sites de comércio eletrônico na medição da conversão. É possível combinar essa métrica com qualquer dimensão para ver quais valores de dimensão contribuíram para quantos produtos foram comprados. Por exemplo, você pode ver as campanhas principais (usando a dimensão do código [de](../dimensions/tracking-code.md) rastreamento) ou os termos de pesquisa internos principais (usando uma [eVar](../dimensions/evar.md)) que contribuíram para os produtos comprados.

## Como essa métrica é calculada

Para cada ocorrência em que `purchase` existe na [`events`](/help/implement/vars/page-vars/events/events-overview.md) variável, soma o campo &#39;Quantidade&#39; dentro da [`products`](/help/implement/vars/page-vars/products.md) variável.

## Comparar pedidos e unidades

A métrica [Pedidos](orders.md) registra apenas o número de eventos de compra. A métrica &quot;Unidades&quot; normalmente é maior que &quot;Pedidos&quot;, pois os clientes podem comprar mais de um produto. Nesses casos, existe um único pedido com várias unidades.

Se você tiver pedidos maiores que as unidades, a Adobe recomenda verificar a integridade de sua implementação. É provável que sua `products` variável não esteja definida corretamente em compras, o que normalmente é um comportamento indesejado.
