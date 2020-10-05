---
title: Estado identificado
description: Um sinalizador que determina o reconhecimento pelo gráfico do dispositivo.
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 9%

---


# Estado identificado

A dimensão &quot;Estado identificado&quot; é específica para conjuntos de relatórios virtuais do Analytics [de](../cda/overview.md) vários dispositivos. Ele relata se a ID do Experience Cloud é reconhecida pelo gráfico do dispositivo no momento em que o relatório é executado. Essa dimensão é útil para entender o quão bem o CDA costuma suturar ou &quot;compactar&quot; dados.

## Preencher esta dimensão com dados

Contanto que você tenha o Analytics [de](../cda/overview.md) vários dispositivos configurado para um conjunto de relatórios virtual, essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: O gráfico do dispositivo reconhece a ID da Experience Cloud vinculada à ocorrência.
* **`"Unidentified"`**: O gráfico do dispositivo não reconhece a Experience Cloud ID ou a ocorrência não tem uma Experience Cloud ID.
