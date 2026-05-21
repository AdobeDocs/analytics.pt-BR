---
title: Tempo gasto na página
description: A quantidade de tempo que um visitante passou na página.
feature: Dimensions
exl-id: 55af7286-7c37-48d2-925e-8b7ecb390e7f
TQID: https://experienceleague.adobe.com/2WS7gBdkpaYUvVqgoR5QTrPes2T2GJT5AEFyj9POcHA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 289
ht-degree: 85%

---

# Tempo gasto na página

A [dimensão](overview.md) de &quot;Tempo gasto na página&quot; registra o tempo que um visitante passou na página. As seguintes etapas são utilizadas para medir o cálculo:

1. Para uma determinada ocorrência, verifique o carimbo de data e hora.
2. Compare essa ocorrência com o carimbo de data e hora da próxima ocorrência na visita. Tanto a visualização de página quanto o rastreamento de link são contabilizados.
3. O tempo decorrido entre essas duas ocorrências contribui para o tempo gasto nessa página.

Essa dimensão é importante quando você deseja entender por quanto tempo os visitantes interagem com uma determinada métrica no site.

>[!TIP]
>
>O tempo gasto não é medido durante a última ocorrência da visita, pois não há solicitação de imagem subsequente para medir o tempo decorrido. Esse conceito também se aplica a visitas que consistem em uma única ocorrência (uma rejeição).

Essa dimensão é baseada em ocorrências, o que significa que o valor é diferente para cada ocorrência. Compare essa dimensão com o [Tempo gasto por visita](time-spent-per-visit.md), que é uma dimensão baseada em visitas. Quanto maior o tempo gasto, mais tempo o visitante passou em uma página (ocorrência).

![Tempo gasto na página](../metrics/assets/time-spent2.png)

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Existem várias dimensões para o tempo gasto na página:

* **Tempo gasto na página - classificado**: a quantidade de tempo é classificada. Os itens de dimensão variam de `"Less than 15 seconds"` a `"More than 30 minutes"`. O tempo entre ocorrências normalmente não dura mais de 30 minutos. No entanto, esse tempo pode exceder 30 minutos se forem usadas ocorrências com carimbo de data e hora ou fontes de dados.
* **Tempo gasto na página - granular**: cada número de segundos é um item de dimensão exclusivo.

Consulte [Visão geral do tempo gasto](../metrics/time-spent.md) para obter mais informações gerais sobre o tempo gasto.
