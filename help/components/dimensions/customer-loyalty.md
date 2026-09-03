---
title: Fidelização do cliente
description: Categorias com base no número de compras anteriores feitas por um visitante
feature: Dimensions
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
TQID: https://experienceleague.adobe.com/Essa0dflFlsqwtTQ4JdaSEOkX6T-zEYrQGhgXBWhfcI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 88%

---

# Fidelização do cliente

A [dimensão](overview.md) de &quot;Fidelidade do cliente&quot; informa o número de visitantes do site que fizeram 0 compras anteriores, 1 compra anterior, 2 compras anteriores ou mais de 3 compras anteriores. Essa dimensão é importante para entender como seu site afeta o comportamento de compra. Você também pode usar essa dimensão em um segmento para se concentrar em visitantes que retornam para fazer uma compra, de modo que você possa incentivar comportamentos semelhantes para novos visitantes.

## Preencher esta dimensão com dados

A Adobe preenche automaticamente essa dimensão com base no evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) em sua implementação. Se você implementar o evento `purchase` em seu site, essa dimensão sempre funcionará.

## Itens de dimensão

Os itens de dimensão incluem:

* **Não é um cliente**: no momento da ocorrência, o visitante nunca tinha feito uma compra antes.
* **Novos clientes**: no momento da ocorrência, o visitante tinha feito uma única compra antes.
* **Clientes recorrentes**: no momento da ocorrência, o visitante tinha feito duas compras antes.
* **Clientes fiéis**: no momento da ocorrência, o visitante tinha feito três ou mais compras antes.

Quando um visitante faz uma compra (aciona o `purchase` evento), essa ocorrência e todas as ocorrências subsequentes são movidas para a próxima “classificação”. Por exemplo, se um visitante comprar um produto do seu site pela primeira vez, ele mudará de “Não é um cliente” para “Novos clientes”, com o pedido atribuído a “Novos clientes”. O item de dimensão “Não é um cliente” não pode ter ordens atribuídas a ele.
