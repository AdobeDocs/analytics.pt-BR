---
title: Estado identificado
description: Um sinalizador que determina o reconhecimento pelo gráfico do dispositivo.
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 12%

---


# Estado identificado

A dimensão &#39;Estado identificado&#39; é específica para [conjuntos de relatórios virtuais do Cross-Device Analytics](../cda/overview.md). Ele relata se a ID do Experience Cloud é reconhecida pelo gráfico do dispositivo no momento em que o relatório é executado. Essa dimensão é útil para entender o quão bem o CDA costuma suturar ou &quot;compactar&quot; dados.

## Preencher esta dimensão com dados

Contanto que você tenha [Análises entre dispositivos](../cda/overview.md) configurado para um conjunto de relatórios virtual, essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: O gráfico do dispositivo reconhece a ID da Experience Cloud vinculada à ocorrência.
* **`"Unidentified"`**: O gráfico do dispositivo não reconhece a Experience Cloud ID ou a ocorrência não tem uma Experience Cloud ID.
