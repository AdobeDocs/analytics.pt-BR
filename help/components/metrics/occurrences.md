---
title: Ocorrências
description: O número de ocorrências em que uma variável foi definida ou mantida.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 64%

---

# Ocorrências

A mensagem &quot;Ocorrências&quot; [métrica](overview.md) mostra o número de ocorrências em que uma determinada dimensão foi definida ou mantida. Quando você arrasta uma dimensão no Workspace para uma tela em branco, a Adobe aplica automaticamente essa métrica ao projeto.

## Como essa métrica é calculada

De todas as ocorrências em um conjunto de relatórios, inclua ocorrências nas quais um item de dimensão é definido ou mantido. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem além da ocorrência em que estão definidas. Essa métrica conta os valores inicial e persistente.

## Comparar a métricas semelhantes

* **Ocorrências versus [Instâncias](instances.md)**: a métrica Ocorrências conta ocorrências em que um item de dimensão foi definido ou mantido. A métrica Instâncias não inclui ocorrências em que um item de dimensão é mantido.
* **Ocorrências versus [Exibições de página](page-views.md)**: as ocorrências incluem todos os tipos de ocorrência, incluindo chamadas de rastreamento de exibição de página ([`t()`](/help/implement/vars/functions/t-method.md)), chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) e dados do resumo [Fontes de dados](/help/import/data-sources/overview.md). A métrica Visualizações de página inclui apenas chamadas de rastreamento de visualização de página, excluindo chamadas de rastreamento de link e fontes de dados de resumo.
