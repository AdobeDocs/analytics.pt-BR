---
title: Tempo gasto por visita
description: A quantidade total de tempo que a visita levou.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 11%

---


# Tempo gasto por visita

*Esta página de ajuda descreve como o &quot;Tempo gasto por visita&quot; funciona como suas respectivas dimensões. Consulte a métrica[Tempo gasto por visita](../metrics/time-spent-per-visit.md)para obter mais informações.*

As dimensões &quot;Tempo gasto por visita&quot; registram o tempo que um visitante gastou em toda a visita. Ele usa as seguintes etapas para medir o cálculo:

1. Observe o carimbo de data e hora da primeira ocorrência da visita.
2. Compare essa ocorrência com o carimbo de data e hora da última ocorrência da visita.
3. A quantidade de tempo decorrido entre essas duas ocorrências contribui para o tempo gasto.

Essas dimensões são importantes quando você deseja entender por quanto tempo os visitantes interagem com o site em geral.

>[!TIP] O tempo gasto requer pelo menos duas ocorrências em uma visita para medir o tempo. Visitas que consistem em uma única ocorrência não aparecem nesta dimensão.

Essa dimensão é baseada em visitas, o que significa que o valor se aplica a cada ocorrência na visita e não é alterado. Compare essa dimensão com o [Tempo gasto na página](time-spent-on-page.md), que é uma dimensão baseada em ocorrências.

Essa dimensão está relacionada ao tempo [médio gasto no site](../metrics/average-time-on-site.md) e às métricas [Tempo gasto por visita](../metrics/time-spent-per-visit.md) .

## Preencher esta dimensão com dados

Essas dimensões funcionam da caixa para todas as implementações. Se um conjunto de relatórios contém dados, essas dimensões funcionam.

## Valores de dimensão

Existem várias dimensões para o tempo gasto por visita:

* **Tempo gasto por visita - segmentado**: A quantidade de tempo é armazenada por período. Os valores de dimensão variam de `"Less than 1 minute"` a `"More than 15 hours"`. As visitas normalmente não duram mais de 12 horas; no entanto, as visitas podem exceder 12 horas se estiverem usando ocorrências com carimbo de data e hora ou fontes de dados.
* **Tempo gasto por visita - granular**: Cada número de segundos é um valor de dimensão exclusivo. Essa dimensão não está disponível no Relatórios e análises ou no Data Warehouse.

Consulte Visão geral [do](../metrics/time-spent.md) Tempo gasto para obter mais informações gerais sobre o tempo gasto.
