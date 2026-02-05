---
title: Visitantes únicos
description: O número de IDs de visitantes únicos.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: f26f406848ab26092738089aac64ed9b4fc08019
workflow-type: ht
source-wordcount: '172'
ht-degree: 100%

---

# Visitantes únicos

A [métrica](overview.md) “Visitantes únicos” mostra o número de IDs de visitantes para o item de dimensão. É uma das métricas mais comuns usadas ao determinar o tráfego, pois fornece uma visão geral de alto nível da popularidade de um item de dimensão. Por exemplo, um visitante pode chegar ao seu site todos os dias por um mês, mas ainda assim contam como um visitante único exclusivo.

Se você usar [Análise entre dispositivos](../cda/overview.md), essa métrica será substituída pela métrica [Dispositivos exclusivos](unique-devices.md).

## Visitantes únicos diários, semanais, mensais, trimestrais e anuais

O Analysis Workspace trata visitantes únicos com base na granularidade do relatório. Por exemplo, se você usar a dimensão [Dia](../dimensions/day.md), verá visitantes únicos diários para cada item de dimensão. No entanto, para o total do relatório, ele é desduplicado em visitantes únicos para o intervalo de datas da tabela de forma livre.

## Como essa métrica é calculada

Essa métrica conta o número de IDs de visitante único de um determinado item de dimensão. Consulte [Visão geral de identificação de visitante](/help/implement/id/overview.md) para obter mais informações sobre como o Adobe Analytics identifica visitantes únicos.
