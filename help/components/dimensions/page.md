---
title: Página
description: O nome da página.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 88%

---


# Página

A dimensão “Página” lista os nomes das páginas do site. É uma das dimensões mais comuns usadas no Adobe Analytics, pois fornece informações sobre quais páginas do site têm melhor desempenho.

Essa dimensão está relacionada à [Seção do site](site-section.md) e às dimensões de [Servidor](server.md). A dimensão Página é mais granular, a dimensão Servidor é menos granular e a dimensão Seção do site fica entre as duas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`pageName` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável `pageName`. Se a variável `pageName` não estiver definida, ela voltará a usar o URL da página.

## itens de Dimension

Os itens de Dimension incluem os nomes das páginas do site. Sua organização determina quais itens de dimensão você deseja usar. Algumas organizações usam diretamente `document.title`, enquanto outras formulam uma navegação estrutural personalizada. Independentemente do método usado, verifique se ele é consistente e registre-o em um [documento de design de solução](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>No Reports &amp; Analytics, as métricas de conversão usam atribuição linear para essa dimensão. Por exemplo, a receita é dividida entre todas as páginas visualizadas antes de um evento de `purchase`. O Analysis Workspace usa a última atribuição por padrão, com a opção de usar qualquer modelo de atribuição.
