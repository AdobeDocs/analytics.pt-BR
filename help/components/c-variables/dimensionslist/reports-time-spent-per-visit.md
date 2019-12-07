---
description: 'null'
title: Tempo gasto por visita
topic: Reports
uuid: 76441e36-b7fe-4cf3-8d72-c51d558afa13
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tempo gasto por visita

O Adobe Analytics oferece várias maneiras de determinar o tempo gasto nos relatórios do Analytics. Na maioria dos casos, o tempo gasto é calculado usando as seguintes etapas:

1. Para determinada visita, verifique o carimbo de data e hora da primeira ocorrência.
2. Compare essa ocorrência com o carimbo de data e hora da última ocorrência da visita.
3. O tempo decorrido entre essas duas ocorrências determina o tempo gasto para essa visita.

Ao exibir os dados da dimensão de tempo gasto, lembre-se do seguinte:

* As exibições de página e os tipos de ocorrência de rastreamento de link são considerados ao calcular os dados de tempo gasto.
* O tempo gasto não é medido durante a última ocorrência da visita, pois não há solicitação de imagem subsequente para medir o tempo decorrido.
* Rejeições não podem medir o tempo gasto, pois a visita consiste em uma única ocorrência.

O tempo gasto por visita mede o tempo total decorrido em uma visita. Existem dimensões separadas entre **granular** e **em bucket**.

* **Granular:** cada valor de dimensão é um número diferente de segundos que compõem uma visita.
* **Em bucket:** cada valor de dimensão é um bucket predefinido:
   * Menos de 1 minuto
   * 1 a 5 minutos
   * 5 a 10 minutos
   * 30 a 60 minutos
   * 1 a 2 horas
   * 2 a 5 horas
   * 5 a 10 horas
   * 10 a 15 horas
   * 15+ horas

> As [!NOTE] [Visitas](../c-metrics/metrics-visit.md) normalmente terminam após 12 horas de atividade. No entanto, as visitas podem exceder 12 horas se estiverem usando ocorrências com carimbo de data e hora ou fontes de dados.

Essa dimensão é baseada em visitas. Compare essa dimensão com o [Tempo gasto na página](reports-time-spent-on-page.md), que é uma dimensão baseada em ocorrências.
