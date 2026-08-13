---
title: Categoria
description: A categoria do produto da ocorrência.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
TQID: 'https://experienceleague.adobe.com/3G1qDbtVnRj8At-FU1fNaI8KLboMQvo8NKktinrTbs8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 155
ht-degree: 93%

---

# Categoria

A [dimensão](overview.md) de &quot;Categoria&quot; relata a categoria de produto da ocorrência. Essa dimensão é útil para implementações que utilizam a variável `products` e que desejam ver as métricas sobre categorias do produto, como os mais vendidos ou os mais vistos. Essa dimensão pode ficar em branco se você não tiver nenhum produto em seu site.

## Preencher esta dimensão com dados

Essa dimensão faz referência à primeira parte da sequência de caracteres da variável [`products`](/help/implement/vars/page-vars/products.md). Tudo que aparece antes do primeiro ponto e vírgula (`;`) faz parte dessa dimensão.

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar cada produto em categorias relevantes, utilizando as dimensões “Produto” e “Categoria”.

>[!TIP]
>
>Nas versões anteriores do Adobe Analytics, a dimensão “Categoria” apresentava algumas limitações devido à sua arquitetura de processamento. Essas limitações foram removidas e, desde então, é possível utilizar qualquer métrica e fazer detalhamentos.
