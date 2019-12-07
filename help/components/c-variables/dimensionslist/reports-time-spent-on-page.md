---
description: Apresenta o tempo que cada visitante passou na página
title: Tempo gasto na página
topic: Reports
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tempo gasto na página

O Adobe Analytics oferece várias maneiras de determinar o tempo gasto nos relatórios do Analytics. Na maioria dos casos, o tempo gasto é calculado usando as seguintes etapas:

1. Para determinada ocorrência, verifique o carimbo de data e hora e o valor de dimensão.
2. Compare essa ocorrência com o carimbo de data e hora da próxima ocorrência na visita.
3. O tempo decorrido entre essas duas ocorrências contribui para o tempo gasto para essa página.

Ao exibir os dados da dimensão de tempo gasto, lembre-se do seguinte:

* O tempo gasto leva em consideração a alocação e a expiração.
* As exibições de página e os tipos de ocorrência de rastreamento de link são considerados ao calcular os dados de tempo gasto.
* O tempo gasto não é medido durante a última ocorrência da visita, pois não há solicitação de imagem subsequente para medir o tempo decorrido.
* Rejeições não podem medir o tempo gasto, pois a visita consiste em uma única ocorrência.

O tempo gasto na página mede o tempo decorrido entre as ocorrências em uma visita. Existem dimensões separadas entre **granular** e **em bucket**.

* **Granular:** cada valor de dimensão é um número diferente de segundos gastos entre duas ocorrências.
* **Em bucket:** cada valor de dimensão é um bucket predefinido:
   * Menos de 15 segundos
   * 15 a 29 minutos
   * 1 a 3 minutos
   * 3 a 5 minutos
   * 5 a 10 minutos
   * 10 a 15 minutos
   * 15 a 20 minutos
   * 20 a 30 minutos
   * Mais de 30 minutos

Essa dimensão é baseada em ocorrências e, se usada como um detalhamento, pode fornecer dados mais significativos. Compare essa dimensão com o [Tempo gasto por visita](reports-time-spent-per-visit.md), que é uma dimensão baseada em visita.

![Tempo gasto](/help/components/c-variables/c-metrics/assets/time-spent1.png)
