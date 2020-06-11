---
title: Dias antes da primeira compra
description: O número de dias entre a primeira visita de um visitante e a primeira compra.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Dias antes da primeira compra

A dimensão &quot;Dias antes da primeira compra&quot; relata o número de dias transcorridos entre a primeira vez que um visitante chega ao site e quando ele faz uma compra. Por exemplo, se um visitante efetua uma compra um dia após a primeira visita, qualquer visita ou evento subsequente pertence ao valor da dimensão &quot;1 dia&quot;.

Depois que um visitante faz sua primeira compra, ele pertence ao mesmo valor de dimensão pelo restante da vida útil do cookie do visitante.

## Preencher esta dimensão com dados

A Adobe preenche automaticamente essa dimensão com base no [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) evento em sua implementação. Se você implementar o `purchase` evento em seu site, essa dimensão sempre funcionará.

## Valores de dimensão

Os valores de dimensão incluem o número de dias entre a primeira visita de um visitante ao seu site e a primeira compra. Cada número de dias é um valor de dimensão separado, com &quot;Mesmo dia&quot; ocorrendo onde uma primeira visita do visitante e sua primeira compra ocorreram no mesmo dia.
