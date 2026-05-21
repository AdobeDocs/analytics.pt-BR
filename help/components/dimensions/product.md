---
title: Produto
description: O nome do produto.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
TQID: https://experienceleague.adobe.com/SMFFeSTkQyQoSWNFc8qHJRxYkJQmiJoKd0v4rS6xRKc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 91%

---

# Produto

A [dimensão](overview.md) do &quot;Produto&quot; relata o nome do produto na ocorrência. Essa dimensão é útil para implementações que utilizam a variável `products` e que desejam ver as métricas sobre produtos, como os mais vendidos ou os mais vistos. Essa dimensão pode ficar em branco se você não tiver nenhum produto em seu site.

## Preencher esta dimensão com dados

Essa dimensão faz referência à segunda parte da sequência de caracteres da variável [`products`](/help/implement/vars/page-vars/products.md). Os caracteres entre o primeiro e o segundo ponto-e-vírgula (`;`) preenchem essa dimensão.

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda que você estabeleça uma convenção de nomenclatura consistente para os produtos. As [classificações](../classifications/classifications-overview.md) estão disponíveis se você quiser agrupar produtos de forma diferente ou fornecer um nome mais amigável. A Adobe recomenda o uso das dimensões “Produto” e “Categoria”.
