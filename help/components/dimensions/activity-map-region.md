---
title: Região do Activity Map
description: A região do site em que você clicou.
feature: Dimensions
role: User, Admin
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 5%

---

# Região do Activity Map

A [dimensão](overview.md) de &quot;Região do Activity Map&quot; exibe as regiões do site em que houve mais cliques. Essa dimensão é útil quando você deseja comparar cliques em regiões abrangentes do site, em vez de links individuais. Também é útil para áreas do site que oferecem conteúdo dinâmico. Por exemplo, se você tiver uma página inicial com artigos de notícias em rotação, usar a dimensão [Link de Activity Map](activity-map-link.md) será difícil porque o texto do link muda constantemente. No entanto, como esses links usam a mesma região, é possível analisar o desempenho dessa área, mesmo que os links individuais possam mudar a cada dia.

## Preencher esta dimensão com dados

Esta dimensão recupera dados da [Variável de dados de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`. Se sua implementação usar [Activity Map](/help/analyze/activity-map/overview.md), essa variável de dados de contexto coletará dados automaticamente quando os links forem clicados.

Para um determinado link que foi clicado, verifique o elemento DOM principal quanto ao seguinte (em ordem):

* Um valor no atributo definido por [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) - definido como o atributo `id` por padrão
* Um valor no atributo `aria-label` quando o atributo `role="region"`
* Os elementos semânticos `<header>`, `<main>`, `<footer>` ou `<nav>` (somente SDK da Web)

Se o elemento DOM principal não atender a nenhum dos critérios acima, a pesquisa continuará recursivamente até a hierarquia DOM. Se nenhum elemento correspondente for encontrado, o valor `BODY` será retornado.

## Itens de dimensão

Os itens de Dimension incluem regiões que você rotulou no site. Valores de região específicos dependem de quais atributos são usados e se elementos de HTML semânticos estão presentes.
