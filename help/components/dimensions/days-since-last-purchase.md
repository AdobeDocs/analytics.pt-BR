---
title: Dias desde a última compra
description: O número de dias entre a ocorrência atual e a última compra realizada.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Dias desde a última compra

A dimensão &quot;Dias desde a última compra&quot; mede o tempo decorrido entre a ocorrência atual do visitante e a compra mais recente no momento. Essa dimensão ajuda você a entender o comportamento que os visitantes fazem depois de comprar algo em seu site.

Visitantes que nunca compraram algo não estão incluídos nessa dimensão. Além disso, as ocorrências acionadas antes da primeira compra do visitante também não são incluídas. Somente as ocorrências após a primeira compra do visitante são incluídas.

## Preencher esta dimensão com dados

A Adobe preenche automaticamente essa dimensão com base no [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) evento em sua implementação. Se você implementar o `purchase` evento em seu site, essa dimensão sempre funcionará.

## Itens de dimensão

Os itens de dimensão incluem o número de dias entre uma compra mais recente do visitante e a ocorrência atual. Cada número de dias é um item de dimensão separado, com &quot;Mesmo dia&quot; ocorrendo em que uma compra mais recente do visitante e a ocorrência atual ocorreram no mesmo dia.
