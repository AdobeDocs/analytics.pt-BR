---
title: Categoria
description: A categoria do produto da ocorrência.
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '155'
ht-degree: 100%

---

# Categoria

A dimensão “Categoria” relata a categoria do produto da ocorrência. Essa dimensão é útil para implementações que utilizam a variável `products` e que desejam ver as métricas sobre categorias do produto, como os mais vendidos ou os mais vistos. Essa dimensão pode ficar em branco se você não tiver nenhum produto em seu site.

## Preencher esta dimensão com dados

Essa dimensão faz referência à primeira parte da sequência de caracteres da variável [`products`](/help/implement/vars/page-vars/products.md). Tudo que aparece antes do primeiro ponto e vírgula (`;`) faz parte dessa dimensão.

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar cada produto em categorias relevantes, utilizando as dimensões “Produto” e “Categoria”.

>[!TIP]
>
>Nas versões anteriores do Adobe Analytics, a dimensão “Categoria” apresentava algumas limitações devido à sua arquitetura de processamento. Essas limitações foram removidas e, desde então, é possível utilizar qualquer métrica e fazer detalhamentos.
