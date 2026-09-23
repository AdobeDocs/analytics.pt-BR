---
title: Dias desde a última compra
description: O número de dias entre o hit atual e a última compra feita.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 64%
---
# Dias desde a última compra

A [dimensão](overview.md) de &quot;Dias desde a última compra&quot; mede a quantidade de tempo decorrido entre a ocorrência atual do visitante e sua compra mais recente no momento. Essa dimensão ajuda você a entender o comportamento que os visitantes têm após comprar algo no seu site,

Visitantes que nunca compraram algo não são incluídos nessa dimensão. Além disso, os hits acionados antes da primeira compra do visitante também não são incluídos. Somente hits após a primeira compra do visitante são incluídos.

## Preencher esta dimensão com dados

O Adobe calcula essa dimensão do lado do servidor a partir do histórico de compras do visitante. Não há variável a ser definida; depende do evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) que está sendo implementado no site.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (calculado pela Adobe) |
| **Web SDK / campo XDM** | Nenhum (calculado pela Adobe) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem o número de dias entre a compra mais recente de um visitante e o hit atual. Cada número de dias é um item de dimensão separado, com “Mesmo dia” ocorrendo quando a compra mais recente de um visitante e o hit atual ocorreram no mesmo dia.
