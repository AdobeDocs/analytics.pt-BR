---
title: Nome do bot
description: O nome do bot que correspondeu às Regras de bot.
exl-id: 668c1dce-c603-477a-9df7-dacb649bbf63
source-git-commit: 5ba12c243a8013c52b487d048c54461ebdf7bd85
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Nome do bot

A dimensão &quot;Nome do bot&quot; mostra os nomes de bots que foram detectados usando [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). Essas regras podem ser regras IAB padrão ou regras de bot personalizadas configuradas pela organização. É útil nos casos em que você deseja saber mais sobre quais bots estão visitando seu site ou quais bots geram mais tráfego.

Ocorrências que correspondem [!UICONTROL Regras de bot] são automaticamente filtrados de todos os relatórios do Analytics, com exceção dessa dimensão, [Ocorrências de bot](../metrics/bot-occurrences.md), e [Exibições de página de bot](../metrics/bot-page-views.md). É possível utilizar essa dimensão e essas duas métricas para ver quais dados de bot são excluídos do restante dos relatórios.

Como os relatórios de bot são separados do restante dos dados do conjunto de relatórios, somente as seguintes dimensões e métricas são compatíveis com essa dimensão:

* [Página](page.md)
* Dimensões com base no tempo (por exemplo, [Dia](day.md), [Semana](week.md)ou [Month](month.md))
* [Ocorrências de bot](../metrics/bot-occurrences.md)
* [Exibições de página de bot](../metrics/bot-page-views.md)

Usar qualquer outra dimensão ou métrica com essa dimensão não retorna dados.

## Preencher esta dimensão com dados

Se você ativou [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), essa dimensão coleta dados automaticamente. Se você ainda não tiver ativado [!UICONTROL Regras de bot], essa dimensão não aparece no Analysis Workspace.

## Itens de dimensão

Cada item de dimensão lista o nome do bot que correspondeu aos critérios da IAB ou da regra de bot personalizada.
