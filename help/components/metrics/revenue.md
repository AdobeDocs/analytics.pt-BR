---
title: Receita
description: A quantidade monetária de produtos comprados em todos os pedidos.
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '113'
ht-degree: 100%

---

# Receita

A métrica “Receita” mostra a quantidade monetária de produtos comprados em todos os pedidos. Essa métrica é essencial para sites de comércio eletrônico na medição da conversão. É possível combinar essa métrica com qualquer dimensão para ver quais itens de dimensão contribuíram para a receita. Por exemplo, você pode ver as campanhas principais (usando a dimensão [Código de rastreamento](../dimensions/tracking-code.md)) ou os termos de pesquisa internos principais (usando uma [eVar](../dimensions/evar.md)).

## Como essa métrica é calculada

Para cada ocorrência em que `purchase` existe na variável [`events`](/help/implement/vars/page-vars/events/event-purchase.md), some o campo “Preço” dentro da variável [`products`](/help/implement/vars/page-vars/products.md).

Essa métrica depende da variável [currencyCode](/help/implement/vars/config-vars/currencycode.md) se a moeda na página for diferente da moeda nativa do conjunto de relatórios.
