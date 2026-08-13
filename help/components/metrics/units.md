---
title: Unidades
description: O número total de produtos comprados em todos os pedidos.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
TQID: https://experienceleague.adobe.com/0v4pF0Iv0IzU9K4CQiTy1-IIYgMCaO37E6QTmAAEPXc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 80%

---

# Unidades

A [métrica](overview.md) de &quot;Unidades&quot; mostra o número total de produtos comprados em todos os pedidos. Essa métrica é essencial para sites de comércio eletrônico na medição da conversão. É possível combinar essa métrica com qualquer dimensão para ver quais itens de dimensão contribuíram para a quantidade de produtos comprados. Por exemplo, é possível ver as campanhas principais (utilizando a dimensão [Código de rastreamento](../dimensions/tracking-code.md)) ou os principais termos internos de pesquisa (utilizando uma [eVar](../dimensions/evar.md)) que contribuíram para a compra dos produtos.

## Como essa métrica é calculada

Para cada ocorrência em que `purchase` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md), adicione o campo “Quantidade” dentro da variável [`products`](/help/implement/vars/page-vars/products.md).

## Comparar pedidos e unidades

A métrica [Pedidos](orders.md) registra apenas o número de eventos de compra. A métrica &quot;Unidades&quot; geralmente é maior que &quot;Pedidos&quot;, pois os clientes podem comprar mais de um produto. Nesses casos, existe um único pedido com várias unidades.

Se você tiver os pedidos maiores que as unidades, a Adobe recomenda verificar a integridade de sua implementação. É provável que sua variável `products` não esteja definida corretamente nas compras, o que geralmente é um comportamento indesejado.
