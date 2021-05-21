---
title: Total de segundos gastos
description: O número total de segundos gastos no item de dimensão.
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '201'
ht-degree: 100%

---

# Total de segundos gastos

A métrica “Total de segundos gastos” mostra o número agregado de segundos que um visitante gastou em um determinado item de dimensão. Essa métrica é útil para obter a quantidade bruta de tempo gasto em um determinado item de dimensão, e não médias de tempo como outras métricas de tempo gasto oferecem.

No Report Builder, essa métrica é chamada de “Tempo total gasto”.

## Como essa métrica é calculada

Essa métrica utiliza as seguintes etapas para medir o cálculo:

1. Para uma determinada ocorrência, verifique o carimbo de data e hora.
2. Compare essa ocorrência com o carimbo de data e hora da próxima ocorrência na visita. Tanto a visualização de página quanto o rastreamento de link são contabilizados.
3. A quantidade de segundos decorridos entre as duas ocorrências contribui para o item da dimensão.

Variáveis persistentes, como [eVars](../dimensions/evar.md), contam no total de segundos gastos. As variáveis de tráfego, como [props](../dimensions/prop.md), incluem segundos gastos em chamadas de rastreamento de link subsequentes.

>[!TIP]
>
>O tempo gasto não é medido durante a última ocorrência da visita, pois não há solicitação de imagem subsequente para medir o tempo decorrido. Esse conceito também se aplica a visitas que consistem em uma única ocorrência (uma rejeição).

Consulte [Visão geral do tempo gasto](time-spent.md) para obter mais informações gerais sobre o tempo gasto.
