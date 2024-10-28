---
title: Ocorrências
description: O número de ocorrências em que uma variável foi definida ou mantida.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 0c5062363e10d9b545a3209ebaefcc6fa5d02c8b
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 57%

---

# Ocorrências

A [métrica](overview.md) “Ocorrências” exibe o número de ocorrências em que uma determinada dimensão foi definida ou mantida. Quando você arrasta uma dimensão no Workspace para uma tela em branco, a Adobe aplica automaticamente essa métrica ao projeto.

## Como essa métrica é calculada

De todas as ocorrências em um conjunto de relatórios, inclua ocorrências nas quais um item de dimensão é definido ou mantido. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem além da ocorrência em que estão definidas. Essa métrica conta os valores inicial e persistente.

## Comparar a métricas semelhantes

* **Ocorrências versus [Instâncias](instances.md)**: a métrica Ocorrências conta ocorrências em que um item de dimensão foi definido ou mantido. A métrica Instâncias não inclui ocorrências em que um item de dimensão é mantido.
* **Ocorrências vs. [Exibições de página](page-views.md)**: as ocorrências incluem todos os tipos de ocorrência, incluindo chamadas de rastreamento de exibição de página ([`t()`](/help/implement/vars/functions/t-method.md)), chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) e dados de resumo de [fontes de dados](/help/import/data-sources/overview.md). A métrica Exibições de página inclui apenas chamadas de rastreamento de exibição de página, e não inclui chamadas de rastreamento de link ou fontes de dados de resumo.

## Persistência

Persistência é a capacidade de um determinado valor de dimensão se relacionar a uma métrica além do evento em que está definido. Ele usa uma combinação de alocação e expiração. A Alocação permite determinar qual valor é mantido quando mais de um item de dimensão pode persistir de cada vez em uma única coluna. A Expiração permite determinar por quanto tempo um item de dimensão persiste além do evento em que está definido.

A Persistência está disponível somente em dimensões e é retroativa aos dados aos quais é aplicada. É uma transformação imediata de dados que ocorre antes da aplicação da filtragem ou de outras operações de análise. Se a persistência não estiver ativada, a dimensão se relacionará somente às métricas que existem no mesmo evento.