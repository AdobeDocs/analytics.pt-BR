---
title: Categoria
description: A categoria do produto da ocorrência.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 85%

---


# Categoria

A dimensão “Categoria” relata a categoria do produto da ocorrência. Essa dimensão é útil para implementações que utilizam a variável `products` e que desejam ver as métricas sobre categorias do produto, como os mais vendidos ou os mais vistos. Essa dimensão pode ficar em branco se você não tiver nenhum produto em seu site.

## Preencher esta dimensão com dados

Essa dimensão faz referência à primeira parte da sequência de caracteres da variável [`products`](/help/implement/vars/page-vars/products.md). Tudo que aparece antes do primeiro ponto e vírgula (`;`) faz parte dessa dimensão.

## itens de Dimension

Como essa variável se baseia em uma sequência de caracteres personalizada na implementação, sua organização determina quais itens de dimensão são. A Adobe recomenda agrupar cada produto em categorias relevantes, utilizando as dimensões “Produto” e “Categoria”.

>[!TIP]
>
>Nas versões anteriores do Adobe Analytics, a dimensão “Categoria” apresentava algumas limitações devido à sua arquitetura de processamento. Essas limitações foram removidas e, desde então, é possível utilizar qualquer métrica e fazer detalhamentos.
