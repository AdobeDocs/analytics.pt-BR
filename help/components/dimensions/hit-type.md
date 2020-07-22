---
title: Tipo de ocorrência
description: Determina se a ocorrência foi uma ocorrência em primeiro ou segundo plano.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---


# Tipo de ocorrência

A dimensão &#39;Tipo de ocorrência&#39; determina se um aplicativo móvel estava em primeiro ou segundo plano quando a ocorrência foi enviada para os servidores de coleta de dados da Adobe. Essa dimensão só é relevante para conjuntos de relatórios que contêm dados para aplicativos móveis. Os dados do navegador coletados pelo AppMeasurement sempre relatam a ocorrência como &quot;Primeiro plano&quot;.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações do SDK móvel na versão 4.13.6 ou superior. Se você não usar o SDK móvel, todas as ocorrências serão listas no item de dimensão &quot;Primeiro plano&quot;. If &quot;Disable Legacy Reporting and Attribution for Background Hits&quot; is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## Itens de dimensão

Os itens de dimensão incluem `"Foreground"` e `"Background"`. Qualquer ocorrência que não foi enviada em segundo plano de um aplicativo móvel pertence ao item de `"Foreground"` dimensão. Qualquer ocorrência enviada em que o aplicativo móvel estava em segundo plano pertence ao item de `"Background"` dimensão.
