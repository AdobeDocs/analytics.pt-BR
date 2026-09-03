---
title: Visualizações de página
description: O número de vezes que um item de dimensão foi definido ou mantido no Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
TQID: https://experienceleague.adobe.com/ZJOoxc3imuMfVTa7caV5eQ6-XJh0amCRq65ByuANFq0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 169
ht-degree: 100%

---

# Visualizações de página

A [métrica](overview.md) **[!UICONTROL Visualizações de página]** mostra o número de vezes que um determinado item de dimensão foi definido ou mantido em uma página. É uma das métricas mais comuns e básicas nos relatórios.

## Como essa métrica é calculada

Essa métrica conta todas as chamadas de rastreamento de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)) em um conjunto de relatórios. Para dimensões, isso inclui ocorrências em que um item de dimensão é definido ou mantido. Isso não inclui chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) ou dados de [Fontes de dados](/help/import/data-sources/overview.md).

## Comparar com métricas semelhantes

* **Visualizações de página vs [visitas](visits.md)**: as Visualizações de página contam o número de vezes que uma página é exibida. A métrica Visitas conta o número de sessões para visitantes. Uma visita consiste em uma ou mais visualizações de página.
* **Visualizações de página vs. [Eventos de página](page-events.md)**: as Visualizações de página contam o número de chamadas de rastreamento de exibição de página (`t()`) e excluem as chamadas de rastreamento de link (`tl()`). Os eventos de página são o oposto. Eles contam o número de chamadas de rastreamento de link e excluem chamadas de rastreamento de visualização de página.
