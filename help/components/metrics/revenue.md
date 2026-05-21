---
title: Receita
description: A quantidade monetária de produtos comprados em todos os pedidos.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
TQID: https://experienceleague.adobe.com/GJsQWf7h-TihzyNUN6e3VGzOUNyxYD1esuvXet5LM1c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 112
ht-degree: 74%

---

# Receita

A [métrica](overview.md) de &quot;Receita&quot; mostra a quantidade monetária de produtos comprados em todos os pedidos. Essa métrica é essencial para sites de comércio eletrônico na medição da conversão. É possível combinar essa métrica com qualquer dimensão para ver quais itens de dimensão contribuíram para a receita. Por exemplo, você pode ver as campanhas principais (usando a dimensão [Código de rastreamento](../dimensions/tracking-code.md)) ou os termos de pesquisa internos principais (usando uma [eVar](../dimensions/evar.md)).

## Como essa métrica é calculada

Para cada ocorrência em que `purchase` existe na variável [`events`](/help/implement/vars/page-vars/events/event-purchase.md), some o campo “Preço” dentro da variável [`products`](/help/implement/vars/page-vars/products.md).

Essa métrica depende da variável [currencyCode](/help/implement/vars/config-vars/currencycode.md) se a moeda na página for diferente da moeda nativa do conjunto de relatórios.
