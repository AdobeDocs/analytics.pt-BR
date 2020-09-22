---
title: Profundidade da ocorrência
description: O número de ocorrências na visita.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '261'
ht-degree: 100%

---


# Profundidade da ocorrência

A dimensão &quot;Profundidade da ocorrência&quot; informa a distância que uma determinada ocorrência está de uma visita. Essa dimensão é importante para entender até que ponto os visitantes fazem ações em seu site. A profundidade da ocorrência conta todos os tipos de ocorrências, incluindo visualizações de página ([`t()`](/help/implement/vars/functions/t-method.md)) e ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem a string `"Hit Depth"` seguida por um número que representa o número de ocorrências na visita. O item de dimensão `"Hit Depth 1"` representa a primeira ocorrência da visita, enquanto o item de dimensão `"Hit Depth 8"` representa a 8ª ocorrência da visita.

## Comparação com a profundidade da visita

A profundidade da ocorrência conta todos os tipos de ocorrências, incluindo visualização de página e ocorrências de rastreamento de link. A profundidade da visita somente aumenta para ocorrências de visualização de página, _e_ o item de dimensão [Página](page.md) não é o mesmo que o valor na página anterior. A profundidade da visita também é uma dimensão que se baseia nas visitas, o que significa que é o mesmo valor para todas as ocorrências na visita. A tabela a seguir descreve um exemplo de visita e como ela considera a profundidade da ocorrência + profundidade da visita:

| Sequência de páginas | Profundidade da ocorrência | Conta para a profundidade da visita? | Profundidade da visita |
| --- | --- | --- | --- |
| Página inicial | 1 | Sim | 4 |
| Página do produto | 2 | Sim | 4 |
| Página inicial | 3 | Sim | 4 |
| Clique no link personalizado | 4 | Não (link personalizado) | 4 |
| Clique no link personalizado | 5 | Não (link personalizado) | 4 |
| Página do produto | 6 | Sim | 4 |
| Clique no link personalizado | 7 | Não (link personalizado) | 4 |
| Página do produto | 8 | Não (igual à página anterior) | 4 |
