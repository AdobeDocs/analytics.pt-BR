---
title: Produto
description: O nome do produto.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---


# Produto

A dimensão &#39;Produto&#39; relata o nome do produto na ocorrência. É útil para implementações que usam a `products` variável e desejam ver métricas em torno de produtos, como os mais vendidos ou os mais vistos. Esta dimensão pode estar intencionalmente em branco se você não tiver nenhum produto em seu site.

## Preencher esta dimensão com dados

Essa dimensão faz referência à segunda parte da string na [`products`](/help/implement/vars/page-vars/products.md) variável. Os caracteres entre o primeiro e o segundo ponto-e-vírgula (`;`) preenchem essa dimensão.

## itens de Dimension

Como essa variável se baseia em uma sequência de caracteres personalizada na implementação, sua organização determina quais itens de dimensão são. A Adobe recomenda que você estabeleça uma convenção de nomenclatura consistente para os produtos. [As classificações](../classifications/c-classifications.md) estão disponíveis se você deseja agrupar produtos de forma diferente ou fornecer um nome mais amigável. O Adobe recomenda o uso das dimensões &quot;Produto&quot; e &quot;Categoria&quot;.
