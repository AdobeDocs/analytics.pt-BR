---
description: O Adobe Analytics oferece várias métricas e dimensões de Tempo gasto. Descubra o que são e como são calculadas.
solution: Analytics
title: Tempo gasto
topic: Metrics
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

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

A quantidade média de tempo gasto no site, normalmente emparelhado com uma dimensão de data. Embora essa métrica normalmente mostre a tendência do tempo gasto ao longo do tempo, também pode ser usada com dimensões como um cálculo alternativo ao Tempo gasto por visita. Seu cálculo aproximado é `Total seconds spent / (Sequences - Bounces)`. Sequências são uma série de ocorrências em que o valor da dimensão não foi alterado.

> [!NOTE] O tempo gasto por visita e o tempo médio gasto no site são métricas semelhantes. A diferença entre essas duas métricas é o seu denominador; o tempo gasto por visita usa `visits - bounces`, enquanto o tempo médio gasto no site usa `sequences - bounces`. Em um nível de visita, essas métricas parecem semelhantes, mas podem ter algumas diferenças em um nível de ocorrência.

## Tempo médio gasto na página

Disponível somente no Construtor de relatórios. Na maioria dos casos, use Tempo gasto por visita.
