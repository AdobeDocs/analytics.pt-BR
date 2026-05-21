---
title: Tempo antes do evento
description: A quantidade de tempo entre a métrica e a primeira ocorrência da visita.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 159
ht-degree: 84%

---

# Tempo antes do evento

A [dimensão](overview.md) de &quot;Tempo antes do evento&quot; relata o tempo decorrido entre a primeira ocorrência da visita e a métrica desejada. Essa dimensão é útil para determinar a quantidade de tempo necessária para obter um evento bem-sucedido, como um envio de formulário ou uma compra.

## Preencher esta dimensão com dados

Tecnicamente, essa dimensão funciona de forma imediata para todas as implementações, no entretanto, funciona melhor com eventos de compra ou personalizados. A Adobe recomenda implementar eventos personalizados em seu site.. Se você implementar eventos personalizados, nenhuma implementação adicional será necessária para essa dimensão.

## Itens de dimensão

Os itens de dimensões incluem intervalos com base no tempo que variam de `"Less than 1 minute"` a `"More than 15 hours"`. Por exemplo, se um visitante levasse 23 minutos da primeira ocorrência até uma compra, ela ficaria abaixo do item de dimensão `"10 to 30 minutes"`. Os intervalos não podem ser personalizados para essa métrica.
