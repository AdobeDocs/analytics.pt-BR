---
title: Profundidade da ocorrência
description: O número de ocorrências na visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 7%

---


# Profundidade da ocorrência

A dimensão &quot;Profundidade de ocorrência&quot; relata o quão distante uma determinada ocorrência está em uma visita. Essa dimensão é importante para entender até que ponto os visitantes fazem ações em seu site. A profundidade da ocorrência conta todos os tipos de ocorrências, incluindo visualizações de página ([`t()`](/help/implement/vars/functions/t-method.md)) e ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios contiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem a string `"Hit Depth"` seguida por um número que representa o número de ocorrências na visita. O item de dimensão de `"Hit Depth 1"` representa a primeira ocorrência da visita, enquanto o item de dimensão representa `"Hit Depth 8"` a 8ª ocorrência da visita.

## Comparação com a profundidade da visita

A profundidade da ocorrência conta todos os tipos de ocorrências, incluindo visualização de página e ocorrências de rastreamento de link. A profundidade da visita somente aumenta para ocorrências de visualização da página _e_ o item de dimensão [Página](page.md) não é o mesmo que o valor na página anterior. A profundidade da visita também é uma dimensão baseada em visita, o que significa que é o mesmo valor para todas as ocorrências na visita. A tabela a seguir descreve um exemplo de visita e como considera a profundidade da ocorrência + profundidade da visita:

| Sequência de páginas | Profundidade da ocorrência | Conta para a profundidade da visita? | Profundidade da visita |
| --- | --- | --- | --- |
| Home page | 1 | Sim | 4 |
| Página do produto | 2 | Sim | 4 |
| Home page | 3 | Sim | 4 |
| Clique no link personalizado | 4 | Não (link personalizado) | 4 |
| Clique no link personalizado | 5 | Não (link personalizado) | 4 |
| Página do produto | 6 | Sim | 4 |
| Clique no link personalizado | 7 | Não (link personalizado) | 4 |
| Página do produto | 8 | Não (igual à página anterior) | 4 |
