---
title: Profundidade da visita
description: Dimensão com base na visita que informa a profundidade da visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 57%

---


# Profundidade da visita

A dimensão &quot;Profundidade da visita&quot; informa o número de visualizações de página que o visitante viu na visita inteira. Visit depth increases only if the hit is a page view, and the [Page](page.md) dimension is not the same as the last page view&#39;s dimension item. É uma dimensão com base na visita, o que significa que contém o mesmo valor para toda a visita. Essa variável é definida para todas as ocorrências em uma visita após a conclusão dessa visita.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## itens de Dimension

Dimension items include the string `"Pages per visit"` followed by a number representing the number of pages in the visit. The dimension item of `"Pages per visit: 1"` represents a single-page visit, while the dimension item `"Pages per visit: 8"` represents a visit with 8 page views (and any number of link tracking calls).

## Comparação com a profundidade da ocorrência

Consulte [Profundidade da ocorrência](hit-depth.md) para obter uma comparação entre dimensões.