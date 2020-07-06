---
title: Página
description: O nome da página.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---


# Página

A dimensão &#39;Página&#39; lista os nomes das páginas do site. É uma das dimensões mais comuns usadas no Adobe Analytics, pois fornece informações sobre quais páginas do site têm melhor desempenho.

Essa dimensão está relacionada à seção [](site-section.md) Site e às dimensões [do Servidor](server.md) . A página é mais granular, o Servidor é menos granular e a seção Site fica entre os dois.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da string [`pageName` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a `pageName` variável. Se a `pageName` variável não estiver definida, ela voltará para o uso do URL da página.

## Valores de dimensão

Os valores de dimensão incluem os nomes das páginas do site. Sua organização determina quais valores de dimensão específicos você deseja usar. Algumas organizações usam diretamente `document.title`, enquanto outras formulam uma navegação estrutural personalizada. Qualquer que seja o método usado, verifique se ele é consistente e se você o registra em um documento [de design de](/help/implement/prepare/solution-design.md)solução.

>[!NOTE]
>
>Em Relatórios e Analytics, as métricas de conversão usam atribuição linear para essa dimensão. For example, revenue is split between all pages viewed in a visit before a `purchase` event. Analysis Workspace usa a última atribuição por padrão, com a opção de usar qualquer modelo de atribuição.
