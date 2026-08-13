---
title: Tempo gasto por visita (dimensões)
description: A quantidade total de tempo da visita.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
TQID: 'https://experienceleague.adobe.com/jtBAAq-Pe0PyCQJPwvzwnK9eLv14CxTvrVQP4lvWy7k'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 304
ht-degree: 91%

---

# Tempo gasto por visita

*Esta página de ajuda descreve como o &quot;Tempo gasto por visita&quot; funciona como suas respectivas [dimensões](overview.md). Consulte a métrica [Tempo gasto por visita](../metrics/time-spent-per-visit.md) para obter mais informações.*

As dimensões “Tempo gasto por visita” registram o tempo que um visitante gastou em toda a visita. As seguintes etapas são utilizadas para medir o cálculo:

1. Observe o carimbo de data e hora da primeira ocorrência da visita.
2. Compare essa ocorrência com o carimbo de data e hora da última ocorrência da visita.
3. O tempo decorrido entre essas duas ocorrências contribui para o tempo gasto nessa página.

Essas dimensões são importantes quando você quer entender por quanto tempo os visitantes interagem com o site em geral.

>[!TIP]
>
>O tempo gasto exige pelo menos duas ocorrências em uma visita para medir o tempo. Visitas que consistem em uma única ocorrência não aparecem nesta dimensão.

Essa dimensão se baseia em visitas, o que significa que o valor se aplica a cada ocorrência na visita e não é alterado. Compare essa dimensão com o [Tempo gasto na página](time-spent-on-page.md), que é uma dimensão que se baseia em ocorrências.

Essa dimensão está relacionada ao [Tempo médio gasto no site](../metrics/average-time-on-site.md) e às métricas [Tempo gasto por visita](../metrics/time-spent-per-visit.md).

## Preencher esta dimensão com dados

Essas dimensões funcionam imediatamente para todas as implementações. Se um conjunto de relatórios tiver dados, essas dimensões funcionam.

## Itens de dimensão

Existem várias dimensões para o tempo gasto por visita:

* **Tempo gasto por visita - classificado**: a quantidade de tempo é classificada. Os itens de dimensão variam de `"Less than 1 minute"` a `"More than 15 hours"`. As visitas normalmente não duram mais de 12 horas; no entanto, as visitas podem exceder 12 horas se estiverem usando ocorrências com carimbo de data e hora ou fontes de dados.
* **Tempo gasto por visita - granular**: cada número de segundos é um item de dimensão exclusivo. Essa dimensão não está disponível no Data Warehouse.

Consulte [Visão geral do tempo gasto](../metrics/time-spent.md) para obter mais informações gerais sobre o tempo gasto.
