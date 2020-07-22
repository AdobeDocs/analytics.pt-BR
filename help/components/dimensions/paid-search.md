---
title: Pesquisa paga
description: Distingue métricas de pesquisa paga e natural.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Pesquisa paga

A dimensão &quot;Pesquisa paga&quot; permite que você veja qualquer métrica e a compare entre a pesquisa paga e a pesquisa natural. Todas as outras ocorrências fora dos mecanismos de pesquisa são omitidas. Essa dimensão é útil para entender como seus esforços de pesquisa paga se comparam com a pesquisa orgânica.

## Preencher esta dimensão com dados

O único requisito para que essa dimensão funcione corretamente é ter a detecção [de pesquisa](/help/admin/admin/paid-search-detection/paid-search-detection.md) paga configurada corretamente nas configurações do conjunto de relatórios. Se a detecção de pesquisa paga estiver configurada corretamente e um conjunto de relatórios tiver dados, essa dimensão sempre funcionará.

## Itens de dimensão

Os itens de dimensão incluem dois valores estáticos: `"Natural"` e `"Paid"`. Se uma visita corresponder aos critérios de um mecanismo de pesquisa e também corresponder à detecção de pesquisa paga, ela pertencerá ao item de `"Paid"` dimensão. Se uma visita corresponder aos critérios de um mecanismo de pesquisa e *não* corresponder à detecção de pesquisa paga, ela pertencerá ao item de `"Natural"` dimensão.
