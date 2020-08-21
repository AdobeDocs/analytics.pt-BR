---
title: Seção do site
description: O nome da seção do site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 82%

---


# Seção do site

A dimensão &quot;Seção do site&quot; lista os nomes das seções do site. Para sites grandes, é útil agrupar páginas em seções. Essa dimensão é útil para ver as seções de site com melhor desempenho ou as mais exibidas.

Essa dimensão está relacionada às dimensões [Página](page.md) e [Servidor](server.md). A dimensão Página é mais granular, a dimensão Servidor é menos granular e a dimensão Seção do site fica entre as duas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`ch` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável [`channel`](/help/implement/vars/page-vars/channel.md).

## itens de Dimension

Os itens de Dimension incluem os nomes das seções do site. Sua organização determina quais itens de dimensão você deseja usar. Independentemente do método usado, verifique se ele é consistente e registre-o em um [documento de design de solução](/help/implement/prepare/solution-design.md).
