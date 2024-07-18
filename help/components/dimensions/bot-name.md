---
title: Nome do bot
description: O nome do bot que correspondeu às Regras de bot.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 7%

---

# Nome do bot 

A [dimensão](overview.md) de &#39;Nome de bot&#39; mostra os nomes de bots que foram detectados usando as [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). Essas regras podem ser regras IAB padrão ou regras de bot personalizadas configuradas pela organização. É útil nos casos em que você deseja saber mais sobre quais bots estão visitando seu site ou quais bots geram mais tráfego.

As ocorrências que correspondem a [!UICONTROL Regras de bot] são automaticamente filtradas de todos os relatórios do Analytics, com exceção a esta dimensão, [Ocorrências de bot](../metrics/bot-occurrences.md) e [Exibições de página de bot](../metrics/bot-page-views.md). É possível utilizar essa dimensão e essas duas métricas para ver quais dados de bot são excluídos do restante dos relatórios.

Como os relatórios de bot são separados do restante dos dados do conjunto de relatórios, somente as seguintes dimensões e métricas são compatíveis com essa dimensão:

* [Página](page.md)
* Dimensões com base em tempo (por exemplo, [Dia](day.md), [Semana](week.md) ou [Mês](month.md))
* [Ocorrências de bot](../metrics/bot-occurrences.md)
* [Exibições de página de bot](../metrics/bot-page-views.md)

Usar qualquer outra dimensão ou métrica com essa dimensão não retorna dados.

## Preencher esta dimensão com dados

Se você tiver habilitado [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), esta dimensão coletará dados automaticamente. Se você ainda não tiver habilitado as [!UICONTROL Regras de bot], esta dimensão não aparecerá no Analysis Workspace.

## Itens de dimensão

Cada item de dimensão lista o nome do bot que correspondeu aos critérios da IAB ou da regra de bot personalizada.
