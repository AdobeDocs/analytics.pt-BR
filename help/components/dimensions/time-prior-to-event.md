---
title: Tempo antes do evento
description: A quantidade de tempo entre a métrica e a primeira ocorrência da visita.
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
source-git-commit: 2c363dce63768101356a6f43ea1e45ae8dd7b139
workflow-type: ht
source-wordcount: '157'
ht-degree: 100%

---

# Tempo antes do evento

A dimensão “Tempo antes do evento” relata a quantidade de tempo decorrido entre a primeira ocorrência da visita e a métrica desejada. Essa dimensão é útil para determinar a quantidade de tempo necessária para obter um evento bem-sucedido, como um envio de formulário ou uma compra.

## Preencher esta dimensão com dados

Tecnicamente, essa dimensão funciona de forma imediata para todas as implementações, no entretanto, funciona melhor com eventos de compra ou personalizados. A Adobe recomenda implementar eventos personalizados em seu site.. Se você implementar eventos personalizados, nenhuma implementação adicional será necessária para essa dimensão.

## Itens de dimensão

Os itens de dimensões incluem intervalos com base no tempo que variam de `"Less than 1 minute"` a `"More than 15 hours"`. Por exemplo, se um visitante levasse 23 minutos da primeira ocorrência até uma compra, ela ficaria abaixo do item de dimensão `"10 to 30 minutes"`. Os intervalos não podem ser personalizados para essa métrica.
