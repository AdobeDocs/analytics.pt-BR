---
title: Ocorrências
description: O número de ocorrências em que uma variável foi definida ou mantida.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 67%

---


# Ocorrências

A métrica “Ocorrências” exibe o número de ocorrências em que uma determinada dimensão foi definida ou mantida. Quando você arrasta uma dimensão no Workspace para uma tela em branco, a Adobe aplica automaticamente essa métrica ao projeto.

## Como essa métrica é calculada

De todas as ocorrências em um conjunto de relatórios, inclua ocorrências nas quais um item de dimensão é definido ou persistente. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem além da ocorrência em que estão definidas. Essa métrica conta os valores inicial e persistente.

## Comparar a métricas semelhantes

* **Ocorrências vs.[Instâncias](instances.md)**: Ocorrências contam ocorrências em que um item de dimensão foi definido ou persistido. As instâncias não incluem ocorrências em que um item de dimensão persiste.
* **Ocorrências versus[Visualizações de página](page-views.md)**: a métrica Ocorrências inclui todos os tipos de ocorrência, incluindo chamadas de rastreamento de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)) e chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)). A métrica Visualizações de página inclui somente chamadas de rastreamento de visualização da página e exclui chamadas de rastreamento de link.
