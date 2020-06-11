---
title: Ocorrências
description: O número de ocorrências que uma variável foi definida ou persistiu.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 1%

---


# Ocorrências

A métrica &#39;Ocorrências&#39; mostra o número de ocorrências em que uma determinada dimensão foi definida ou persistiu. Quando você arrasta uma dimensão no Workspace para uma tela em branco, a Adobe aplica automaticamente essa métrica ao projeto.

## Como essa métrica é calculada

De todas as ocorrências em um conjunto de relatórios, inclua ocorrências nas quais um valor de dimensão é definido ou persistente. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem além da ocorrência em que estão definidas. Métricas como visualizações [de](page-views.md) página e [Ocorrências](occurrences.md) contam valores iniciais e persistentes. Essa métrica não conta valores persistentes.

## Comparar a métricas semelhantes

* **Ocorrências vs.[Instâncias](instances.md)**: Ocorrências contam ocorrências em que um valor de dimensão foi definido ou persistido. As instâncias não incluem ocorrências em que um valor de dimensão persiste.
* **Ocorrências vs. visualizações[de](page-views.md)**página: As ocorrências incluem todos os tipos de ocorrência, incluindo chamadas de rastreamento de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)) e chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)). A métrica visualizações da página inclui somente chamadas de rastreamento de visualização da página e exclui chamadas de rastreamento de link.