---
title: Estado identificado
description: Um sinalizador que determina o reconhecimento pelo gráfico do dispositivo.
translation-type: ht
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: ht
source-wordcount: '120'
ht-degree: 100%

---


# Estado identificado

A dimensão &quot;Estado identificado&quot; é específica para conjuntos de relatórios virtuais do [Cross-Device Analytics](../cda/overview.md). Ele relata se a Experience Cloud ID é reconhecida pelo gráfico do dispositivo no momento em que o relatório é executado. Essa dimensão é útil para entender o quão bem o CDA costuma compilar ou &quot;compactar&quot; dados.

## Preencher esta dimensão com dados

Se o [Cross-Device Analytics](../cda/overview.md) estiver configurado para um conjunto de relatórios virtual, essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: O gráfico do dispositivo reconhece a Experience Cloud ID vinculada ao hit.
* **`"Unidentified"`**: O gráfico do dispositivo não reconhece a Experience Cloud ID ou o hit não tem uma Experience Cloud ID.
