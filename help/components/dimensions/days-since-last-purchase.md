---
title: Dias desde a última compra
description: O número de dias entre a ocorrência atual e a última compra feita.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 84%

---

# Dias desde a última compra

A [dimensão](overview.md) de &quot;Dias desde a última compra&quot; mede a quantidade de tempo decorrido entre a ocorrência atual do visitante e sua compra mais recente no momento. Essa dimensão ajuda você a entender o comportamento que os visitantes têm após comprar algo no seu site,

Visitantes que nunca compraram algo não são incluídos nessa dimensão. Além disso, as ocorrências acionadas antes da primeira compra do visitante também não são incluídas. Somente as ocorrências após a primeira compra do visitante são incluídas.

## Preencher esta dimensão com dados

A Adobe preenche automaticamente essa dimensão com base no evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) em sua implementação. Se você implementar o evento `purchase` em seu site, essa dimensão sempre funcionará.

## Itens de dimensão

Os itens de dimensão incluem o número de dias entre a compra mais recente de um visitante e a ocorrência atual. Cada número de dias é um item de dimensão separado, com “Mesmo dia” ocorrendo quando a compra mais recente de um visitante e a ocorrência atual ocorreram no mesmo dia.
