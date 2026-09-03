---
title: Página do Activity Map
description: O nome da página quando um link foi clicado.
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
TQID: https://experienceleague.adobe.com/WJ0uk-LqIABwehzzy79c2o1cd3EvI-AKUJ--vmLnKRE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 6%

---

# Página do Activity Map

A [dimensão](overview.md) da &#39;Página do Activity Map&#39; exibe a página em que um visitante estava quando um link foi clicado. É possível usar essa dimensão para determinar quais páginas contêm links que são mais clicados. Essa dimensão também é usada pela sobreposição do Activity Map para determinar quais links exibir.

## Preencher esta dimensão com dados

Esta dimensão recupera dados da [Variável de dados de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. Se sua implementação usa o [Activity Map](/help/analyze/activity-map/overview.md), esta variável de dados de contexto coleta dados automaticamente quando os links são clicados.

Para um determinado link que foi clicado, essa variável de dados de contexto coleta o valor na dimensão [Página](page.md). Se a dimensão Página não contiver um valor, a dimensão [URL da página](page-url.md) será usada (de forma semelhante ao fallback que a dimensão Página usa). Os dados do Activity Map normalmente são enviados na próxima ocorrência depois que um link é clicado. Essa dimensão permite determinar o valor da página quando o link foi clicado, em vez do valor da página quando os dados foram enviados.

## Itens de dimensão

Os itens de Dimension incluem todos os valores encontrados na dimensão [Página](page.md).
