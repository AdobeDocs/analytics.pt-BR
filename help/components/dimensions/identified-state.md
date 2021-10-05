---
title: Estado identificado
description: Um sinalizador que determina o reconhecimento pelo gráfico do dispositivo.
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: 1a58c3e87f5918c91b891faa6027f5ad8b6024b9
workflow-type: ht
source-wordcount: '111'
ht-degree: 100%

---

# Estado identificado

A dimensão &quot;Estado identificado&quot; é específica para conjuntos de relatórios virtuais do [Cross-Device Analytics](../cda/overview.md). Ele relata se as ocorrências são identificadas (compiladas) ou não pelo sistema no momento em que o relatório é executado. Essa dimensão é útil para entender o quão bem o CDA costuma compilar ou &quot;compactar&quot; dados.

## Preencher esta dimensão com dados

Se o [Cross-Device Analytics](../cda/overview.md) estiver configurado para um conjunto de relatórios virtual, essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: o hit é mapeado para uma pessoa.
* **`"Unidentified"`**: o hit não é mapeado para uma pessoa e não pode ser mapeado por nenhum método de atribuição.
