---
title: Pesquisa paga
description: Distingue métricas de pesquisa paga e natural.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
source-git-commit: 35e7c8bccb8524fa5e87cae223f0854956c7528a
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 100%

---

# Pesquisa paga

A dimensão “Pesquisa paga” permite que você veja qualquer métrica e a compare entre a pesquisa paga e a pesquisa natural. Todas as outras ocorrências fora dos mecanismos de pesquisa são omitidas. Essa dimensão é útil para entender como seus esforços de pesquisa paga se comparam com a pesquisa orgânica.

## Preencher esta dimensão com dados

O único requisito para que essa dimensão funcione corretamente é ter a [Detecção de pesquisa paga](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) definida corretamente nas configurações do conjunto de relatórios. Se a detecção de pesquisa paga estiver configurada corretamente e um conjunto de relatórios tiver dados, essa dimensão sempre funcionará.

## Itens de dimensão

Os itens de dimensão têm dois valores estáticos: `"Natural"` e `"Paid"`. Se uma visita corresponder aos critérios de um mecanismo de pesquisa e também corresponder à detecção de pesquisa paga, ela pertencerá ao item de dimensão `"Paid"`. Se uma visita corresponder aos critérios de um mecanismo de pesquisa e *não* corresponder à detecção de pesquisa paga, ela pertencerá ao item de dimensão `"Natural"`.
