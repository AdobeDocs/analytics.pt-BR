---
title: Estado identificado
description: Um sinalizador que determina o reconhecimento pelo gráfico do dispositivo.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 89%

---

# Estado identificado

A [dimensão](overview.md) de &#39;Estado identificado&#39; é específica para os conjuntos de relatórios virtuais do [Cross-Device Analytics](../cda/overview.md). Ele relata se as ocorrências são identificadas (compiladas) ou não pelo sistema no momento em que o relatório é executado. Essa dimensão é útil para entender o quão bem o CDA costuma compilar ou &quot;compactar&quot; dados.

## Preencher esta dimensão com dados

Se o [Cross-Device Analytics](../cda/overview.md) estiver configurado para um conjunto de relatórios virtual, essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: o hit é mapeado para uma pessoa.
* **`"Unidentified"`**: o hit não é mapeado para uma pessoa e não pode ser mapeado por nenhum método de atribuição.
