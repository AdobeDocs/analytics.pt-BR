---
title: Link por região do Activity Map
description: Um valor concatenado de link e região.
feature: Dimensions
role: User, Admin
source-git-commit: 65e75a1c2b39823e72abfb0e5b61122c62f1f013
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 11%

---

# Link por região do Activity Map

A [dimensão](overview.md) do &#39;Link Activity Map Por Região&#39; exibe uma concatenação de [Link Activity Map](activity-map-link.md) e [Região Activity Map](activity-map-link-by-region.md). Essa dimensão é útil quando você tem links com nomes semelhantes, mas que residem em regiões diferentes do site. Por exemplo, se você tiver vários links para sua página inicial rotulados como &quot;Página inicial&quot;, poderá usar essa dimensão para distinguir esses links em cada região do site.

## Preencher esta dimensão com dados

Esta dimensão recupera dados das [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link` e `c.a.activitymap.region`. Esses dois valores são concatenados e separados por uma barra vertical (`|`). Se sua implementação usar [Activity Map](/help/analyze/activity-map/overview.md), essas variáveis de dados de contexto coletarão dados automaticamente quando os links forem clicados.

## Itens de dimensão

Os itens de Dimension incluem valores de [Activity Map Link](activity-map-link.md) e [Região de Activity Map](activity-map-link-by-region.md). A estrutura do site e a implementação da organização determinam os valores exatos coletados.
