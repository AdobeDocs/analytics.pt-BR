---
title: Região do Activity Map
description: A região do site em que você clicou.
feature: Dimensions
role: User, Admin
exl-id: e262e537-ce73-492a-8ab3-b88cd77cb8c5
TQID: https://experienceleague.adobe.com/mmLp5-dgKGeovIOMPZxliyhfbpUSMLXca-3Qs6QA0SA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 5%

---

# Região do Activity Map

A [dimensão](overview.md) de &quot;Região do Activity Map&quot; exibe as regiões do site em que mais se clicou. Essa dimensão é útil quando você deseja comparar cliques em regiões abrangentes do site, em vez de links individuais. Também é útil para áreas do site que oferecem conteúdo dinâmico. Por exemplo, se você tiver uma página inicial com artigos de notícias em rotação, usar a dimensão [Link do Activity Map](activity-map-link.md) será difícil porque o texto do link muda constantemente. No entanto, como esses links usam a mesma região, é possível analisar o desempenho dessa área, mesmo que os links individuais possam mudar a cada dia.

## Preencher esta dimensão com dados

Esta dimensão recupera dados da [Variável de dados de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`. Se sua implementação usa o [Activity Map](/help/analyze/activity-map/overview.md), esta variável de dados de contexto coleta dados automaticamente quando os links são clicados.

Para um determinado link que foi clicado, verifique o elemento DOM principal quanto ao seguinte (em ordem):

* Um valor no atributo definido por [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) - definido como o atributo `id` por padrão
* Um valor no atributo `aria-label` quando o atributo `role="region"`
* Os elementos semânticos `<header>`, `<main>`, `<footer>` ou `<nav>` (somente Web SDK)

Se o elemento DOM principal não atender a nenhum dos critérios acima, a pesquisa continuará recursivamente até a hierarquia DOM. Se nenhum elemento correspondente for encontrado, o valor `BODY` será retornado.

## Itens de dimensão

Os itens do Dimension incluem regiões que você rotulou no site. Valores de região específicos dependem de quais atributos são usados e se elementos de HTML semânticos estão presentes.
