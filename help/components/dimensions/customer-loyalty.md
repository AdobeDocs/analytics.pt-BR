---
title: Fidelização do cliente
description: Categorias com base no número de compras anteriores feitas por um visitante
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
source-wordcount: '280'
ht-degree: 73%
---
# Fidelização do cliente

A [dimensão](overview.md) de &quot;Fidelidade do cliente&quot; informa o número de visitantes do site que fizeram 0 compras anteriores, 1 compra anterior, 2 compras anteriores ou mais de 3 compras anteriores. Essa dimensão é importante para entender como seu site afeta o comportamento de compra. Você também pode usar essa dimensão em um segmento para se concentrar em visitantes que retornam para fazer uma compra, de modo que você possa incentivar comportamentos semelhantes para novos visitantes.

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

Os itens de dimensão incluem:

* **Não é um cliente**: no momento do hit, o visitante nunca tinha feito uma compra antes.
* **Novos clientes**: no momento do hit, o visitante tinha feito uma única compra antes.
* **Clientes recorrentes**: no momento do hit, o visitante tinha feito duas compras antes.
* **Clientes fiéis**: no momento do hit, o visitante tinha feito três ou mais compras antes.

Quando um visitante faz uma compra (aciona o `purchase` evento), esse hit e todos os hits subsequentes são movidos para a próxima “classificação”. Por exemplo, se um visitante comprar um produto do seu site pela primeira vez, ele mudará de “Não é um cliente” para “Novos clientes”, com o pedido atribuído a “Novos clientes”. O item de dimensão “Não é um cliente” não pode ter ordens atribuídas a ele.
