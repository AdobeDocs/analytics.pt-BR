---
title: Link do Activity Map por região
description: Um valor concatenado de link e região.
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
TQID: https://experienceleague.adobe.com/xvYVA064hA0rsBdnLpxXllq3PD0zYAikFRjc6xNErvg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 151
ht-degree: 11%

---

# Link do Activity Map por região

A [dimensão](overview.md) do &#39;Link por Região do Activity Map&#39; exibe uma concatenação do [Link do Activity Map](activity-map-link.md) e da [Região do Activity Map](activity-map-link-by-region.md). Essa dimensão é útil quando você tem links com nomes semelhantes, mas que residem em regiões diferentes do site. Por exemplo, se você tiver vários links para sua página inicial rotulados como &quot;Página inicial&quot;, poderá usar essa dimensão para distinguir esses links em cada região do site.

## Preencher esta dimensão com dados

Esta dimensão recupera dados das [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link` e `c.a.activitymap.region`. Esses dois valores são concatenados e separados por uma barra vertical (`|`). Se sua implementação usa o [Activity Map](/help/analyze/activity-map/overview.md), essas variáveis de dados de contexto coletam dados automaticamente quando os links são clicados.

## Itens de dimensão

Os itens do Dimension incluem valores de [Activity Map Link](activity-map-link.md) e [Activity Map Region](activity-map-link-by-region.md). A estrutura do site e a implementação da organização determinam os valores exatos coletados.
