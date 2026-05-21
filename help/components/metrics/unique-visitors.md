---
title: Visitantes únicos
description: O número de IDs de visitantes únicos.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
TQID: https://experienceleague.adobe.com/A0NvwoGPFLuS4e857eH-nMgmzAmz0EuGVQVDNBgiN4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 100%

---

# Visitantes únicos

A [métrica](overview.md) “Visitantes únicos” mostra o número de IDs de visitantes para o item de dimensão. É uma das métricas mais comuns usadas ao determinar o tráfego, pois fornece uma visão geral de alto nível da popularidade de um item de dimensão. Por exemplo, um visitante pode chegar ao seu site todos os dias por um mês, mas ainda assim contam como um visitante único exclusivo.

Se você usar [Análise entre dispositivos](../cda/overview.md), essa métrica será substituída pela métrica [Dispositivos exclusivos](unique-devices.md).

## Visitantes únicos diários, semanais, mensais, trimestrais e anuais

O Analysis Workspace trata visitantes únicos com base na granularidade do relatório. Por exemplo, se você usar a dimensão [Dia](../dimensions/day.md), verá visitantes únicos diários para cada item de dimensão. No entanto, para o total do relatório, ele é desduplicado em visitantes únicos para o intervalo de datas da tabela de forma livre.

## Como essa métrica é calculada

Essa métrica conta o número de IDs de visitante único de um determinado item de dimensão. Consulte [Visão geral de identificação de visitante](/help/implement/id/overview.md) para obter mais informações sobre como o Adobe Analytics identifica visitantes únicos.
