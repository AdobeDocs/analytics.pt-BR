---
title: Carrinhos
description: O número de ocorrências em que um visitante adicionou seu primeiro produto ao carrinho.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Carrinhos

A métrica &#39;Remoções do carrinho&#39; mostra o número de vezes que um visitante removeu algo do carrinho. Essa métrica é útil quando você deseja entender a parte do funil de conversão em que os clientes não estão mais interessados em um produto.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências em que `scOpen` existe na [`events`](/help/implement/vars/page-vars/events/events-overview.md) variável.

## Diferença entre &quot;Carrinhos&quot; e &quot;visualizações do carrinho&quot;

Como &quot;Carrinhos&quot; e &quot;visualizações de carrinho&quot; são eventos que exigem implementação, sua organização decide a diferença precisa entre essas duas métricas. No entanto, a Adobe projetou essas métricas para o seguinte:

* &quot;Carrinhos&quot; dispara apenas uma vez por compra quando um visitante adiciona seu primeiro produto ao carrinho de compras.
* Os acionadores de &#39;adições ao carrinho&#39; para cada produto adicionado ao carrinho.

Para o primeiro produto, são acionados &quot;Carrinhos&quot; e &quot;Adições ao carrinho&quot;. Mais uma vez, estas orientações não são concretas; sua organização determina a lógica de implementação exata.
