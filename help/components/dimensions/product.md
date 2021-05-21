---
title: Produto
description: O nome do produto.
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---

# Produto

A dimensão “Produto” informa o nome do produto na ocorrência. Essa dimensão é útil para implementações que utilizam a variável `products` e que desejam ver as métricas sobre produtos, como os mais vendidos ou os mais vistos. Essa dimensão pode ficar em branco se você não tiver nenhum produto em seu site.

## Preencher esta dimensão com dados

Essa dimensão faz referência à segunda parte da sequência de caracteres da variável [`products`](/help/implement/vars/page-vars/products.md). Os caracteres entre o primeiro e o segundo ponto-e-vírgula (`;`) preenchem essa dimensão.

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda que você estabeleça uma convenção de nomenclatura consistente para os produtos. As [classificações](../classifications/c-classifications.md) estão disponíveis se você quiser agrupar produtos de forma diferente ou fornecer um nome mais amigável. A Adobe recomenda o uso das dimensões “Produto” e “Categoria”.
