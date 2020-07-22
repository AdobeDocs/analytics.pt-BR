---
title: Média de visualizações de página por visita
description: O número médio de vezes que um determinado item de dimensão apareceu em uma visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---


# Média de visualizações de página por visita

A dimensão &#39;Média de visualizações de página por visita&#39; mostra quantas visualizações de página ocorreram em média em relação à dimensão desejada. Para dimensões baseadas em tempo, você pode ver como o número médio de visualizações de página dentro de uma visita tende ao longo do tempo. Essa métrica é útil quando você deseja entender com que frequência os itens de dimensão aparecem em uma visita.

>[DICA] Use essa métrica junto com outra métrica (como [Visitas](visits.md)) para obter melhores insights. Se você usar essa métrica sozinho, você obterá itens de dimensão que contêm visualizações de página de anomalia por visita, o que normalmente não é valioso.

## Como essa métrica é calculada

Essa métrica é calculada usando a fórmula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é a média de visualizações de página de toda a dimensão por visita, e o numerador é a média de visualizações de página do item de dimensão por visita. Se a média de visualizações de página de toda a dimensão por visita for menor que a média de visualizações de página de um determinado item de dimensão por visita, você verá percentuais acima de 100%. A classificação de relatórios classificados por essa métrica mostra a média de anomalias das visualizações de página por valores de visita, o que normalmente não é valioso. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.