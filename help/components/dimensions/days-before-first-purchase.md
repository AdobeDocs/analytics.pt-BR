---
title: Dias antes da primeira compra
description: O número de dias entre a primeira visita e a primeira compra.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 83%

---

# Dias antes da primeira compra

A [dimensão](overview.md) de &quot;Dias antes da primeira compra&quot; informa o número de dias que se passam entre a primeira vez que um visitante acessa seu site e quando ele faz uma compra. Por exemplo, se um visitante efetua uma compra um dia após a primeira visita, qualquer visita ou evento subsequente pertence ao item de dimensão “1 dia”.

Depois que um visitante faz a primeira compra, ele pertence ao mesmo item de dimensão pelo restante da vida útil do cookie do visitante.

## Preencher esta dimensão com dados

A Adobe preenche automaticamente essa dimensão com base no evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) em sua implementação. Se você implementar o evento `purchase` em seu site, essa dimensão sempre funcionará.

## Itens de dimensão

Os itens de dimensão incluem o número de dias entre a primeira visita ao seu site e a primeira compra. Cada número de dias é um item de dimensão separado, com o “Mesmo dia” ocorrendo quando uma primeira visita e sua primeira compra ocorreram no mesmo dia.
