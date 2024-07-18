---
title: Categoria
description: A categoria do produto da ocorrência.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '155'
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
