---
title: Visualizações de produto
description: O número de visualizações para páginas do produtos.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
TQID: https://experienceleague.adobe.com/bspBkiEAfkwBQwWV3-KoDKDRNGLogCKkSXvY2Cpyv-M
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 80
ht-degree: 72%

---

# Visualizações de produto

A [métrica](overview.md) de &#39;Exibições de produto&#39; mostra o número de vezes que qualquer produto foi exibido. Essa métrica é útil quando você deseja ver seus produtos mais vistos, ou ver a tendência total das visualizações de produtos ao longo do tempo.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências que correspondem a **qualquer** uma das seguintes opções:

* O valor `prodView` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md); ou
* A variável [`products`](/help/implement/vars/page-vars/products.md) está definida e a variável `events` está vazia.
