---
title: Visão geral das dimensões
description: Variáveis que contêm valores de string.
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
source-git-commit: 3ed4c075578ef31cec4b1c825039eae989c813dc
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 100%

---

# Visão geral das dimensões

Dimensões são variáveis no Adobe Analytics que normalmente contêm valores de string. As dimensões comuns incluem [Página](page.md), [Domínio de referência](referring-domain.md) ou uma [eVar](evar.md). Por outro lado, as [métricas](../metrics/overview.md) contêm valores numéricos que se vinculam a uma dimensão. Um relatório básico mostra linhas de valores da sequência de caracteres (dimensão) em relação a uma coluna de valores numéricos (métrica).

Por exemplo, ao combinar a dimensão &quot;Página&quot; com a métrica &quot;Visitas&quot;, é possível obter um relatório classificado que mostra as páginas mais visitadas:

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

Cada dimensão representa uma parte ou uma faceta diferente do site. É possível combinar uma ou mais dessas dimensões com uma ou mais métricas para criar o relatório desejado.

## Adicionar descrições de dimensão

Os administradores do Analytics podem adicionar descrições de dimensões e outros componentes dentro do conjunto de relatórios ou diretamente do Analysis Workspace. Para obter informações sobre como adicionar descrições a dimensões, consulte [Adicionar descrições de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).
