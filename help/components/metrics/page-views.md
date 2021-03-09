---
title: 'Métrica de Visualizações de página explicada | Adobe Analytics '
description: Saiba como a métrica de visualizações de página é trabalhada no Adobe Analytics e também entenda a diferença entre visitas e visualizações de página.
translation-type: ht
source-git-commit: c588087b949093152435967f62e43758e9e86208
workflow-type: ht
source-wordcount: '176'
ht-degree: 100%

---


# Saiba mais sobre Visualizações de página com o Adobe Analytics

A métrica “Visualizações de página” mostra o número de vezes que um determinado item de dimensão foi definido ou persistiu em uma página. É uma das métricas mais comuns e básicas nos relatórios.

## Como essa métrica é calculada

Essa métrica conta todas as chamadas de rastreamento de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)) em um conjunto de relatórios. Para dimensões, inclui ocorrências em que um item de dimensão é definido ou persistente. Ela não inclui chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Comparar a métricas semelhantes

* **Visualizações de página versus [visitas](visits.md)**: as visualizações de página contam o número de vezes que uma página é visualizada. A métrica Visitas conta o número de sessões para visitantes. Uma visita consiste em uma ou mais páginas.
* **Visualizações de página versus [Eventos de página](page-events.md)**: as visualizações de página contam o número de chamadas de rastreamento de visualização de página (`t()`) e excluem chamadas de rastreamento de link (`tl()`). Eventos de página é o oposto; conta o número de chamadas de rastreamento de link e exclui visualizações de página.