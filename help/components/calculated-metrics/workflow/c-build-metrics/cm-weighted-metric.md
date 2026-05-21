---
description: Saiba mais sobre exemplos de métricas filtradas e ponderadas.
title: Métricas Filtradas E Ponderadas
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
TQID: https://experienceleague.adobe.com/Euk3sI0-AYtfmpEbL-8gfWU4HcFE6kGO6QGgctZbvig
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 158
ht-degree: 9%

---

# Métricas filtradas e ponderadas

Este artigo mostra exemplos de métricas filtradas e ponderadas.

## Taxa de rejeição filtrada

Essa métrica filtrada simples mostra a taxa de rejeição somente para páginas com mais de 100 visitas:

![Taxa de rejeição filtrada](assets/filtered-bounce-rate.png){zoomable="yes"}

Lembre-se de que essa fórmula depende de um intervalo de tempo consistente. Se você executar um relatório por um único dia, qualquer página com mais de 20 visitas vale a pena analisá-la. Se você o executar por um mês, pode querer que o filtro inclua mais visitas.

## Taxa de rejeição filtrada com percentual

Esse filtro mostra a taxa de rejeição para os primeiros 30% das páginas, quando classificadas por visitas.

![Taxa de rejeição filtrada com percentil](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}

## Taxa de rejeição ponderada

Suponha que você queira classificar por taxa de rejeição em geral, mas as páginas com mais visitas devem estar em maior posição na lista. Você pode criar uma Taxa de rejeição ponderada com a seguinte aparência:

![](assets/weighted-bounce-rate.png)
