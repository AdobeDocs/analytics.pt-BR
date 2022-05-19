---
title: Carrinhos
description: O número de ocorrências em que um visitante adicionou seu primeiro produto ao carrinho.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: 932a6c1452d4710b11c1ce5551c845ef6721f137
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 56%

---

# Carrinhos

A métrica &quot;Carrinhos&quot; mostra o número de hits em que um visitante adicionou o primeiro produto ao carrinho.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências em que `scOpen` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Diferença entre &quot;Carrinhos&quot;, &quot;Visualizações do carrinho&quot; e &quot;Adições ao carrinho&quot;

Como &quot;Carrinhos&quot;, &quot;Visualizações do carrinho&quot; e &quot;Adições ao carrinho&quot; são eventos que exigem implementação, sua organização decide a diferença precisa entre essas métricas. No entanto, o Adobe projetou essas métricas para a seguinte lógica:

* A métrica “Carrinhos” é acionada apenas uma vez por compra quando um visitante adiciona seu primeiro produto ao carrinho de compras.
* As &quot;Visualizações do carrinho&quot; são acionadas toda vez que um visitante exibe seu carrinho de compras.
* A métrica “Adições ao carrinho” é acionada para cada produto adicionado ao carrinho.

Quando um cliente adiciona seu primeiro produto a um carrinho de compras, o comportamento pretendido é o acionamento de &quot;Carrinhos&quot; e &quot;Adições ao carrinho&quot;. Mais uma vez, estas orientações não são concretas; a organização determina a lógica de implementação exata.
