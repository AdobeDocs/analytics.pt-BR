---
title: Product
description: O nome do produto.
translation-type: tm+mt
source-git-commit: bddfc52d460e87a70e7cff149f197570f405037a
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---


# Product

A dimensão &#39;Produto&#39; relata o nome do produto na ocorrência. É útil para implementações que usam a `products` variável e desejam ver métricas em torno de produtos, como os mais vendidos ou os mais vistos. Esta dimensão pode estar intencionalmente em branco se você não tiver nenhum produto em seu site.

## Preencher esta dimensão com dados

Essa dimensão faz referência à segunda parte da string na [`products`](/help/implement/vars/page-vars/products.md) variável. Os caracteres entre o primeiro e o segundo ponto-e-vírgula (`;`) preenchem essa dimensão.

## Valores de dimensão

Como essa variável se baseia em uma sequência de caracteres personalizada na implementação, sua organização determina quais são os valores da dimensão. A Adobe recomenda que você estabeleça uma convenção de nomenclatura consistente para os produtos. [As classificações](../c-classifications2/c-classifications.md) estão disponíveis se você deseja agrupar produtos de forma diferente ou fornecer um nome mais amigável. A Adobe recomenda usar as dimensões &quot;Produto&quot; e &quot;Categoria&quot;.
