---
title: Profundidade da visita
description: Dimensão com base na visita que informa a profundidade da visita.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
TQID: https://experienceleague.adobe.com/mT5dQzR6edNpvU6Fbf9LlLwQuxW6RA-ZCZJDaIFkyAw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 90%

---

# Profundidade da visita

A [dimensão](overview.md) de &quot;Profundidade da visita&quot; informa o número de exibições de página que o visitante viu na visita inteira. A profundidade da visita aumenta somente se a ocorrência for uma visualização de página e a dimensão [Página](page.md) não for a mesma que o item da última dimensão de visualização de página. É uma dimensão com base na visita, o que significa que contém o mesmo valor para toda a visita. Essa variável é definida para todas as ocorrências em uma visita após a conclusão dessa visita.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem a string `"Pages per visit"` seguida por um número que representa o número de páginas na visita. O item de dimensão de `"Pages per visit: 1"` representa uma visita de página única, enquanto o item de dimensão `"Pages per visit: 8"` representa uma visita com 8 visualizações de página (e qualquer número de chamadas de rastreamento de link).

## Comparação com a profundidade da ocorrência

Consulte [Profundidade da ocorrência](hit-depth.md) para obter uma comparação entre dimensões.
