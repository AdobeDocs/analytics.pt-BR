---
title: Estado identificado
description: Um sinalizador que determina o reconhecimento para compilação.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: f75a1f6d9f08f422595c24760796abf0f8332ddb
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 83%

---

# Estado identificado

A [dimensão](overview.md) de &#39;Estado identificado&#39; é específica para os conjuntos de relatórios virtuais do [Cross-Device Analytics](../cda/overview.md). Ele relata se as ocorrências são identificadas (compiladas) ou não pelo sistema no momento em que o relatório é executado. Essa dimensão é útil para entender o quão bem o CDA costuma compilar ou &quot;compactar&quot; dados.

## Preencher esta dimensão com dados

Se o [Cross-Device Analytics](../cda/overview.md) estiver configurado para um conjunto de relatórios virtual, essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: o hit é mapeado para uma pessoa.
* **`"Unidentified"`**: o hit não é mapeado para uma pessoa e não pode ser mapeado por nenhum método de atribuição.
