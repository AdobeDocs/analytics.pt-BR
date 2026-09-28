---
title: Dias antes da primeira compra
description: O número de dias entre a primeira visita e a primeira compra.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
TQID: 'https://experienceleague.adobe.com/fA8CgahXKwJfiynK-I8yuD-byaIyFPkaii3FzkrrPoI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 63%
---
# Dias antes da primeira compra

A [dimensão](overview.md) de &quot;Dias antes da primeira compra&quot; informa o número de dias que se passam entre a primeira vez que um visitante acessa seu site e quando ele faz uma compra. Por exemplo, se um visitante efetua uma compra um dia após a primeira visita, qualquer visita ou evento subsequente pertence ao item de dimensão “1 dia”.

Depois que um visitante faz a primeira compra, ele pertence ao mesmo item de dimensão pelo restante da vida útil do cookie do visitante.

## Preencher esta dimensão com dados

O Adobe calcula essa dimensão do lado do servidor a partir do histórico de compras do visitante. Não há variável a ser definida; depende do evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) que está sendo implementado no site.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (calculado pela Adobe) |
| **Web SDK / campo XDM** | Nenhum (calculado pela Adobe) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | Visitante |

## Itens de dimensão

Os itens de dimensão incluem o número de dias entre a primeira visita ao seu site e a primeira compra. Cada número de dias é um item de dimensão separado, com o “Mesmo dia” ocorrendo quando uma primeira visita e sua primeira compra ocorreram no mesmo dia.
