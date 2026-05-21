---
title: Carrinhos
description: O número de ocorrências em que um visitante adicionou seu primeiro produto ao carrinho.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
TQID: https://experienceleague.adobe.com/a-qT5Ly8-4mSBGbGTAzbwLIMRFZtqotMPvGFgOrM41Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 45%

---

# Carrinhos

A [métrica](overview.md) de &quot;Carrinhos&quot; mostra o número de ocorrências em que um visitante adicionou seu primeiro produto ao carrinho.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências em que `scOpen` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Diferença entre &quot;Carrinhos&quot;, &quot;Visualizações do carrinho&quot; e &quot;Adições ao carrinho&quot;

Como as métricas &quot;Carrinhos&quot;, &quot;Visualizações de carrinho&quot; e &quot;Adições ao carrinho&quot; são eventos que exigem implementação, sua organização decide a diferença exata entre essas métricas. No entanto, a Adobe projetou essas métricas para a seguinte lógica:

* A métrica “Carrinhos” é acionada apenas uma vez por compra quando um visitante adiciona seu primeiro produto ao carrinho de compras.
* A métrica &quot;Visualizações do carrinho&quot; é acionada sempre que um visitante exibe seu carrinho de compras.
* A métrica “Adições ao carrinho” é acionada para cada produto adicionado ao carrinho.

Quando um cliente adiciona seu primeiro produto a um carrinho de compras, o comportamento pretendido é que as métricas &quot;Carrinhos&quot; e &quot;Adições ao carrinho&quot; sejam acionadas. Mais uma vez, estas orientações não são concretas; a organização determina a lógica de implementação exata.
