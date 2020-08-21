---
title: Carrinhos
description: O número de ocorrências em que um visitante adicionou seu primeiro produto ao carrinho.
translation-type: ht
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: ht
source-wordcount: '157'
ht-degree: 100%

---


# Carrinhos

A métrica “Remoções do carrinho” mostra o número de vezes que um visitante removeu algo do carrinho. Essa métrica ajuda a entender a parte do funil de conversão em que os clientes não estão mais interessados em um produto.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências em que `scOpen` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Diferença entre &quot;Carrinhos&quot; e &quot;Visualizações do carrinho&quot;

Como as métricas &quot;Carrinhos&quot; e &quot;Visualizações de carrinho&quot; são eventos que exigem implementação, a própria organização decide a diferença exata entre essas duas métricas. No entanto, a Adobe projetou essas métricas para o seguinte:

* A métrica “Carrinhos” é acionada apenas uma vez por compra quando um visitante adiciona seu primeiro produto ao carrinho de compras.
* A métrica “Adições ao carrinho” é acionada para cada produto adicionado ao carrinho.

Para o primeiro produto, são acionadas as métricas &quot;Carrinhos&quot; e &quot;Adições ao carrinho&quot;. Mais uma vez, estas orientações não são concretas; a organização determina a lógica de implementação exata.
