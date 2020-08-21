---
title: Tempo antes do evento
description: A quantidade de tempo entre a métrica e a primeira ocorrência da visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 78%

---


# Tempo antes do evento

A dimensão “Tempo antes do evento” relata a quantidade de tempo decorrido entre a primeira ocorrência da visita e a métrica desejada. Essa dimensão é útil para determinar a quantidade de tempo necessária para obter um evento bem-sucedido, como um envio de formulário ou uma compra.

## Preencher esta dimensão com dados

Tecnicamente, essa dimensão funciona de forma imediata para todas as implementações, no entretanto, funciona melhor com eventos de compra ou personalizados. A Adobe recomenda implementar eventos personalizados em seu site.. Se você implementar eventos personalizados, nenhuma implementação adicional será necessária para essa dimensão.

## itens de Dimension

Dimension items include time-based buckets ranging from `"Less than 1 minute"` to `"More than 15 hours"`. For example, if it took a visitor 23 minutes from their first hit to a purchase, it would belong under the `"10 to 30 minutes"` dimension item.
