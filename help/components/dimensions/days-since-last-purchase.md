---
title: Dias desde a última compra
description: O número de dias entre a ocorrência atual e a última compra feita.
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '173'
ht-degree: 100%

---

# Dias desde a última compra

A dimensão “Dias desde a última compra” mede o tempo decorrido entre a ocorrência atual do visitante e sua compra mais recente no momento. Essa dimensão ajuda você a entender o comportamento que os visitantes têm após comprar algo no seu site,

Visitantes que nunca compraram algo não são incluídos nessa dimensão. Além disso, as ocorrências acionadas antes da primeira compra do visitante também não são incluídas. Somente as ocorrências após a primeira compra do visitante são incluídas.

## Preencher esta dimensão com dados

A Adobe preenche automaticamente essa dimensão com base no evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) em sua implementação. Se você implementar o evento `purchase` em seu site, essa dimensão sempre funcionará.

## Itens de dimensão

Os itens de dimensão incluem o número de dias entre a compra mais recente de um visitante e a ocorrência atual. Cada número de dias é um item de dimensão separado, com “Mesmo dia” ocorrendo quando a compra mais recente de um visitante e a ocorrência atual ocorreram no mesmo dia.
