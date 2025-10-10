---
title: Link do Activity Map por região
description: Um valor concatenado de link e região.
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 11%

---

# Link do Activity Map por região

A [dimensão](overview.md) do &#39;Link por Região do Activity Map&#39; exibe uma concatenação do [Link do Activity Map](activity-map-link.md) e da [Região do Activity Map](activity-map-link-by-region.md). Essa dimensão é útil quando você tem links com nomes semelhantes, mas que residem em regiões diferentes do site. Por exemplo, se você tiver vários links para sua página inicial rotulados como &quot;Página inicial&quot;, poderá usar essa dimensão para distinguir esses links em cada região do site.

## Preencher esta dimensão com dados

Esta dimensão recupera dados das [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link` e `c.a.activitymap.region`. Esses dois valores são concatenados e separados por uma barra vertical (`|`). Se sua implementação usa o [Activity Map](/help/analyze/activity-map/overview.md), essas variáveis de dados de contexto coletam dados automaticamente quando os links são clicados.

## Itens de dimensão

Os itens do Dimension incluem valores de [Activity Map Link](activity-map-link.md) e [Activity Map Region](activity-map-link-by-region.md). A estrutura do site e a implementação da organização determinam os valores exatos coletados.
