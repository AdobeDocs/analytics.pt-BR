---
title: Nome do bot
description: O nome do bot que corresponde às regras de bot.
exl-id: 668c1dce-c603-477a-9df7-dacb649bbf63
hide: true
hidefromtoc: true
source-git-commit: 017559d2b909deb4bf87fb5fe41db8250f2ca2ac
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Nome do bot

A dimensão &quot;Nome do bot&quot; mostra os nomes dos bots que foram detectados usando [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). Essas regras podem ser regras IAB padrão ou regras de bot personalizadas que sua organização configura. É útil nos casos em que você deseja saber mais sobre quais bots estão visitando seu site ou quais bots geram mais tráfego.

Ocorrências que correspondem [!UICONTROL Regras de bot] são filtrados automaticamente de todos os relatórios do Analytics, com exceção desta dimensão, [Ocorrências de bot](../metrics/bot-occurrences.md)e [Exibições da página de bot](../metrics/bot-page-views.md). É possível usar essa dimensão e essas duas métricas para ver quais dados de bot são excluídos do restante dos relatórios.

Como os relatórios de bot são separados do restante dos dados do conjunto de relatórios, somente as seguintes dimensões e métricas são compatíveis com essa dimensão:

* [Página](page.md)
* Dimensões baseadas em tempo (por exemplo, [Dia](day.md), [Semana](week.md)ou [Mês](month.md))
* [Ocorrências de bot](../metrics/bot-occurrences.md)
* [Exibições da página de bot](../metrics/bot-page-views.md)

Usar qualquer outra dimensão ou métrica com essa dimensão não retorna dados.

## Preencher esta dimensão com dados

Se você ativou [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), essa dimensão coleta dados automaticamente. Se você ainda não tiver ativado [!UICONTROL Regras de bot], essa dimensão não é exibida no Analysis Workspace.

## Itens de dimensão

Cada item de dimensão lista o nome do bot que corresponde aos critérios da regra de bot personalizada ou IAB.
