---
title: Dias antes da primeira compra
description: O número de dias entre a primeira visita e a primeira compra.
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '173'
ht-degree: 100%

---

# Dias antes da primeira compra

A dimensão “Dias antes da primeira compra” informa o número de dias que se passam entre a primeira vez que um visitante acessa seu site e quando ele faz uma compra. Por exemplo, se um visitante efetua uma compra um dia após a primeira visita, qualquer visita ou evento subsequente pertence ao item de dimensão “1 dia”.

Depois que um visitante faz a primeira compra, ele pertence ao mesmo item de dimensão pelo restante da vida útil do cookie do visitante.

## Preencher esta dimensão com dados

A Adobe preenche automaticamente essa dimensão com base no evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) em sua implementação. Se você implementar o evento `purchase` em seu site, essa dimensão sempre funcionará.

## Itens de dimensão

Os itens de dimensão incluem o número de dias entre a primeira visita ao seu site e a primeira compra. Cada número de dias é um item de dimensão separado, com o “Mesmo dia” ocorrendo quando uma primeira visita e sua primeira compra ocorreram no mesmo dia.
