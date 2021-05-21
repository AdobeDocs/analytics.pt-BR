---
title: Profundidade da visita
description: Dimensão com base na visita que informa a profundidade da visita.
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '166'
ht-degree: 100%

---

# Profundidade da visita

A dimensão &quot;Profundidade da visita&quot; informa o número de visualizações de página que o visitante viu na visita inteira. A profundidade da visita aumenta somente se a ocorrência for uma visualização de página e a dimensão [Página](page.md) não for a mesma que o item da última dimensão de visualização de página. É uma dimensão com base na visita, o que significa que contém o mesmo valor para toda a visita. Essa variável é definida para todas as ocorrências em uma visita após a conclusão dessa visita.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem a string `"Pages per visit"` seguida por um número que representa o número de páginas na visita. O item de dimensão de `"Pages per visit: 1"` representa uma visita de página única, enquanto o item de dimensão `"Pages per visit: 8"` representa uma visita com 8 visualizações de página (e qualquer número de chamadas de rastreamento de link).

## Comparação com a profundidade da ocorrência

Consulte [Profundidade da ocorrência](hit-depth.md) para obter uma comparação entre dimensões.
