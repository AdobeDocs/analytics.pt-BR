---
title: Instâncias
description: O número de ocorrências que uma variável foi definida (e não persistiu).
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---


# Instâncias

A métrica &#39;Instâncias&#39; mostra o número de vezes que uma dimensão foi explicitamente definida em uma solicitação de imagem. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem valores de dimensão após a ocorrência em que estão definidas. Essa métrica é útil quando você deseja ver o número de vezes que um valor de dimensão foi definido sem as ocorrências nas quais esse valor persistiu.

## Como essa métrica é calculada

De todas as ocorrências em um conjunto de relatórios, inclua somente ocorrências que definam explicitamente um valor de dimensão na solicitação de imagem. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem além da ocorrência em que estão definidas. Métricas como visualizações [de](page-views.md) página e [Ocorrências](occurrences.md) contam valores iniciais e persistentes. Essa métrica não conta valores persistentes.