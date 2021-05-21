---
title: Tipo de ocorrência
description: Determina se a ocorrência foi uma ocorrência em primeiro ou segundo plano.
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# Tipo de ocorrência

A dimensão “Tipo de ocorrência” determina se um aplicativo móvel estava em primeiro ou segundo plano quando a ocorrência foi enviada para os servidores de coleta de dados da Adobe. Essa dimensão só é relevante para conjuntos de relatórios que contêm dados para aplicativos móveis. Os dados do navegador coletados pelo AppMeasurement sempre relatam a ocorrência como “Primeiro plano”.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações do SDK móvel na versão 4.13.6 ou superior. Se você não usar o SDK móvel, todas as ocorrências serão listas no item de dimensão “Primeiro plano”. Se “Desativar os relatórios herdados e a atribuição para ocorrências em segundo plano” estiver marcado, as ocorrências em segundo plano serão exibidas apenas nos [Conjuntos de relatórios virtuais](../vrs/vrs-mobile-visit-processing.md).

## Itens de dimensão

Os itens de dimensão incluem `"Foreground"` e `"Background"`. Qualquer ocorrência que não foi enviada em segundo plano de um aplicativo móvel pertence ao item de dimensão `"Foreground"`. Qualquer ocorrência enviada em que o aplicativo móvel estava em segundo plano pertence ao item de dimensão `"Background"`.
