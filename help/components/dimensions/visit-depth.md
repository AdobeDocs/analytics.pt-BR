---
title: Profundidade da visita
description: Dimensão baseada em visita que relata a profundidade da visita.
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Profundidade da visita

A dimensão &quot;Profundidade da visita&quot; relata o número de visualizações de página que o visitante viu na visita inteira. A profundidade da visita aumenta somente se a ocorrência for uma visualização de página e a dimensão [Página](page.md) não for a mesma que o valor da última dimensão de visualização de página. É uma dimensão baseada em visita, o que significa que contém o mesmo valor para toda a visita. Essa variável é definida para todas as ocorrências em uma visita após a conclusão dessa visita.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios contiver dados, essa dimensão funcionará.

## Valores de dimensão

Os valores de dimensão incluem a string `"Pages per visit"` seguida por um número que representa o número de páginas na visita. O valor de dimensão de `"Pages per visit: 1"` representa uma visita de página única, enquanto o valor de dimensão `"Pages per visit: 8"` representa uma visita com 8 visualizações de página (e qualquer número de chamadas de rastreamento de link).

## Comparação com a profundidade da ocorrência

Consulte Profundidade [da](hit-depth.md) ocorrência para obter uma comparação entre dimensões.