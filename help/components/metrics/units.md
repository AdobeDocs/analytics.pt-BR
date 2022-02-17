---
title: Unidades
description: O número total de produtos comprados em todos os pedidos.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 100%

---

# Unidades

A métrica “Unidades” exibe o número total de produtos comprados em todos os pedidos. Essa métrica é essencial para sites de comércio eletrônico na medição da conversão. É possível combinar essa métrica com qualquer dimensão para ver quais itens de dimensão contribuíram para a quantidade de produtos comprados. Por exemplo, é possível ver as campanhas principais (utilizando a dimensão [Código de rastreamento](../dimensions/tracking-code.md)) ou os principais termos internos de pesquisa (utilizando uma [eVar](../dimensions/evar.md)) que contribuíram para a compra dos produtos.

## Como essa métrica é calculada

Para cada ocorrência em que `purchase` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md), adicione o campo “Quantidade” dentro da variável [`products`](/help/implement/vars/page-vars/products.md).

## Comparar pedidos e unidades

A métrica [Pedidos](orders.md) registra apenas o número de eventos de compra. A métrica &quot;Unidades&quot; geralmente é maior que &quot;Pedidos&quot;, pois os clientes podem comprar mais de um produto. Nesses casos, existe um único pedido com várias unidades.

Se você tiver os pedidos maiores que as unidades, a Adobe recomenda verificar a integridade de sua implementação. É provável que sua variável `products` não esteja definida corretamente nas compras, o que geralmente é um comportamento indesejado.
