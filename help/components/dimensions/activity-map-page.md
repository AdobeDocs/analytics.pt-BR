---
title: Página do Activity Map
description: O nome da página quando um link foi clicado.
feature: Dimensions
role: User, Admin
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# Página do Activity Map

A [dimensão](overview.md) da &#39;Página de Activity Map&#39; exibe a página em que um visitante estava quando um link foi clicado. É possível usar essa dimensão para determinar quais páginas contêm links que são mais clicados. Essa dimensão também é usada pela sobreposição de Activity Map para determinar quais links exibir.

## Preencher esta dimensão com dados

Esta dimensão recupera dados da [Variável de dados de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. Se sua implementação usar [Activity Map](/help/analyze/activity-map/overview.md), essa variável de dados de contexto coletará dados automaticamente quando os links forem clicados.

Para um determinado link que foi clicado, essa variável de dados de contexto coleta o valor na dimensão [Página](page.md). Se a dimensão Página não contiver um valor, a dimensão [URL da página](page-url.md) será usada (de forma semelhante ao fallback que a dimensão Página usa). Os dados de Activity Map normalmente são enviados na próxima ocorrência depois que um link é clicado. Essa dimensão permite determinar o valor da página quando o link foi clicado, em vez do valor da página quando os dados foram enviados.

## Itens de dimensão

Os itens de Dimension incluem todos os valores encontrados na dimensão [Página](page.md).
