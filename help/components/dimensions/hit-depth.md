---
title: Profundidade da ocorrência
description: O número de ocorrências na visita.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 94%

---

# Profundidade da ocorrência

A [dimensão](overview.md) de &quot;Profundidade da ocorrência&quot; relata a distância que uma determinada ocorrência está de uma visita. Essa dimensão é importante para entender até que ponto os visitantes fazem ações em seu site. A profundidade da ocorrência conta todos os tipos de ocorrências, incluindo visualizações de página ([`t()`](/help/implement/vars/functions/t-method.md)) e ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).

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
