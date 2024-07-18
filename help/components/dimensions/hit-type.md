---
title: Tipo de ocorrência
description: Determina se a ocorrência foi uma ocorrência em primeiro ou segundo plano.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 84%

---

# Tipo de ocorrência

A [dimensão](overview.md) do &quot;Tipo de ocorrência&quot; determina se um aplicativo móvel estava em primeiro ou segundo plano quando a ocorrência foi enviada para os servidores de coleta de dados do Adobe. Essa dimensão só é relevante para conjuntos de relatórios que contêm dados para aplicativos móveis. Os dados do navegador coletados pelo AppMeasurement sempre relatam a ocorrência como “Primeiro plano”.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações do SDK móvel na versão 4.13.6 ou superior. Se você não usar o SDK móvel, todas as ocorrências serão listas no item de dimensão “Primeiro plano”. Se “Desativar os relatórios herdados e a atribuição para ocorrências em segundo plano” estiver marcado, as ocorrências em segundo plano serão exibidas apenas nos [Conjuntos de relatórios virtuais](../vrs/vrs-mobile-visit-processing.md).

## Itens de dimensão

Os itens de dimensão incluem `"Foreground"` e `"Background"`. Qualquer ocorrência que não foi enviada em segundo plano de um aplicativo móvel pertence ao item de dimensão `"Foreground"`. Qualquer ocorrência enviada em que o aplicativo móvel estava em segundo plano pertence ao item de dimensão `"Background"`.
