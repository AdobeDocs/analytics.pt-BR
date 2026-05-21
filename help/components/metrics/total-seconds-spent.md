---
title: Total de segundos gastos
description: O número total de segundos gastos no item de dimensão.
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
TQID: https://experienceleague.adobe.com/FQ5FGTOKnJph7C0jWwbcAHA31yUwz7ewQRPykUD6R0E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 90%

---

# Total de segundos gastos

A [métrica](overview.md) de &quot;Total de segundos gastos&quot; mostra o número agregado de segundos que um visitante gastou em um determinado item de dimensão. Essa métrica é útil para obter a quantidade bruta de tempo gasto em um determinado item de dimensão, e não médias de tempo como outras métricas de tempo gasto oferecem.

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
