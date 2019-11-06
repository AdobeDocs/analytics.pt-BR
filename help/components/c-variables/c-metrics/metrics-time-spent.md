---
description: O Adobe Analytics oferece várias métricas e dimensões de Tempo gasto. Descubra o que são e como são calculadas.
solution: Analytics
title: Tempo gasto
topic: Métricas
translation-type: tm+mt
source-git-commit: ee9a6462138fe3483ca8a4ba042cb4eb39536031

---


# Métricas de tempo gasto

O Adobe Analytics oferece várias maneiras de determinar o tempo gasto nos relatórios do Analytics. Na maioria dos casos, o tempo gasto é calculado usando as seguintes etapas:

1. Para uma determinada ocorrência, verifique o carimbo de data e hora e o valor da dimensão.
1. Compare essa ocorrência com o carimbo de data e hora da próxima ocorrência na visita.
1. A quantidade de tempo decorrido entre essas duas ocorrências contribui para o tempo gasto para esse valor de dimensão.

Ao exibir as métricas de tempo gasto, lembre-se do seguinte:

* O tempo gasto leva a alocação e a expiração em conta.
* As exibições de página e os tipos de ocorrência de rastreamento de link são considerados ao calcular os dados de tempo gasto.
* O tempo gasto não é medido durante a última ocorrência da visita, pois não há solicitação de imagem subsequente para medir o tempo decorrido.
* Rejeições não podem medir o tempo gasto, pois a visita consiste em uma única ocorrência.

## Total de segundos gastos

A quantidade total de tempo que todos os visitantes interagiram com um valor de dimensão, medido em segundos.

## Tempo gasto por visita (segundos)

A quantidade média de tempo que os visitantes interagem com um valor de dimensão em uma visita. Seu cálculo aproximado é `Total seconds spent / (Visits - Bounces)`.

## Tempo gasto por visitante (segundos)

A quantidade média de tempo que os visitantes interagem com um valor de dimensão ao longo da vida útil do visitante. Seu cálculo aproximado é `Total seconds spent / (Unique Visitors - Bounces)`.

## Tempo médio gasto no site (segundos)

O tempo médio gasto no site com o valor de dimensão especificado. Normalmente, essa métrica é emparelhada com uma dimensão de data para mostrar o tempo gasto ao longo do tempo. Seu cálculo aproximado é `Total seconds spent / (Sequences - Bounces)`. Sequências são uma série de ocorrências em que o valor da dimensão não foi alterado. Na maioria dos casos, use Tempo gasto por visita.

## Tempo médio gasto na página

Disponível somente no Construtor de relatórios. Na maioria dos casos, use Tempo gasto por visita.
