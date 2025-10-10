---
title: Página do Activity Map
description: O nome da página quando um link foi clicado.
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# Página do Activity Map

A [dimensão](overview.md) da &#39;Página do Activity Map&#39; exibe a página em que um visitante estava quando um link foi clicado. É possível usar essa dimensão para determinar quais páginas contêm links que são mais clicados. Essa dimensão também é usada pela sobreposição do Activity Map para determinar quais links exibir.

## Preencher esta dimensão com dados

Esta dimensão recupera dados da [Variável de dados de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. Se sua implementação usa o [Activity Map](/help/analyze/activity-map/overview.md), esta variável de dados de contexto coleta dados automaticamente quando os links são clicados.

Para um determinado link que foi clicado, essa variável de dados de contexto coleta o valor na dimensão [Página](page.md). Se a dimensão Página não contiver um valor, a dimensão [URL da página](page-url.md) será usada (de forma semelhante ao fallback que a dimensão Página usa). Os dados do Activity Map normalmente são enviados na próxima ocorrência depois que um link é clicado. Essa dimensão permite determinar o valor da página quando o link foi clicado, em vez do valor da página quando os dados foram enviados.

## Itens de dimensão

Os itens de Dimension incluem todos os valores encontrados na dimensão [Página](page.md).
