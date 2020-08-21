---
title: Total de segundos gastos
description: O número total agregado de segundos gastos no item de dimensão.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 64%

---


# Total de segundos gastos

A métrica &#39;Total de segundos gastos&#39; mostra o número agregado de segundos que um visitante gastou em um determinado item de dimensão. Essa métrica é útil quando você deseja a quantidade bruta de tempo gasta em um determinado item de dimensão, e não médias como outras ofertas de métricas de tempo gasto.

No Report Builder, essa métrica é chamada de “Tempo total gasto”.

## Como essa métrica é calculada

Essa métrica utiliza as seguintes etapas para medir o cálculo:

1. Para uma determinada ocorrência, verifique o carimbo de data e hora.
2. Compare essa ocorrência com o carimbo de data e hora da próxima ocorrência na visita. Tanto a visualização de página quanto o rastreamento de link são contabilizados. 
3. A quantidade de segundos decorridos entre as duas ocorrências contribui para o item de dimensão.

Variáveis persistentes, como [eVars](../dimensions/evar.md), contam no total de segundos gastos. As variáveis de tráfego, como [props](../dimensions/prop.md), incluem segundos gastos em chamadas de rastreamento de link subsequentes.

>[!TIP]
>
>O tempo gasto não é medido durante a última ocorrência da visita, pois não há solicitação de imagem subsequente para medir o tempo decorrido. Esse conceito também se aplica a visitas que consistem em uma única ocorrência (uma rejeição).

Consulte [Visão geral do tempo gasto](time-spent.md) para obter mais informações gerais sobre o tempo gasto.
