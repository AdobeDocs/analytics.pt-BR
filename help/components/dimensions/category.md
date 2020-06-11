---
title: Categoria
description: A categoria do produto da ocorrência.
translation-type: tm+mt
source-git-commit: bddfc52d460e87a70e7cff149f197570f405037a
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 1%

---


# Categoria

A dimensão &#39;Categoria&#39; relata a categoria do produto da ocorrência. É útil para implementações que usam a `products` variável e desejam ver métricas em torno da categoria do produto, como os mais vendidos ou os mais vistos. Esta dimensão pode estar intencionalmente em branco se você não tiver nenhum produto em seu site.

## Preencher esta dimensão com dados

Essa dimensão faz referência à primeira parte da string na [`products`](/help/implement/vars/page-vars/products.md) variável. Tudo antes do primeiro ponto e vírgula (`;`) preenche essa dimensão.

## Valores de dimensão

Como essa variável se baseia em uma sequência de caracteres personalizada na implementação, sua organização determina quais são os valores da dimensão. A Adobe recomenda que você agrupe produtos individuais em categorias significativas, usando as dimensões &#39;Produto&#39; e &#39;Categoria&#39;.

> [!TIP] Em versões anteriores do Adobe Analytics, algumas limitações à dimensão &quot;Categoria&quot; eram impostas devido à sua arquitetura de processamento. Essas limitações foram removidas desde então, permitindo que você use qualquer métrica e qualquer detalhamento.
