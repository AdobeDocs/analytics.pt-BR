---
title: Exibições de página
description: O número de vezes que uma página foi visualizada.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 2%

---


# Exibições de página

A métrica &#39;visualizações de página&#39; mostra o número de vezes que um determinado item de dimensão foi definido ou persistiu em uma página. É uma das métricas mais comuns e básicas nos relatórios.

## Como essa métrica é calculada

Essa métrica conta todas as chamadas de rastreamento de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)) em um conjunto de relatórios. Para dimensões, inclui ocorrências em que um item de dimensão é definido ou persistente. Ela não inclui chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Comparar a métricas semelhantes

* **visualizações de página versus[visitas](visits.md)**: As visualizações de página contam o número de vezes que uma página é visualizada. Visitas conta o número de sessões para visitantes. Uma visita consiste em uma ou mais páginas.
* **visualizações de página x eventos[de](page-events.md)**página: As visualizações de página contam o número de chamadas de rastreamento de visualização de página (`t()`) e excluem chamadas de rastreamento de link (`tl()`). eventos de página é o oposto; conta o número de chamadas de rastreamento de link e exclui visualizações de página.