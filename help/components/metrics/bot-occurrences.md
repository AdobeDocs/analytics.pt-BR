---
title: Ocorrências de bot
description: O número de ocorrências que corresponderam às regras de bot.
feature: Metrics
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# Ocorrências de bot

As &#39;Ocorrências de bot&#39; [métrica](overview.md) mostra o número de ocorrências correspondentes a [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Como o relatório de bot é separado do restante dos dados do conjunto de relatórios, essa métrica funciona somente com as seguintes dimensões:

* [Nome do bot ](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensões com base no tempo (por exemplo, [Dia](../dimensions/day.md), [Semana](../dimensions/week.md)ou [Month](../dimensions/month.md))

Usar qualquer outra dimensão com essa métrica não retorna dados.

## Como essa métrica é calculada

O Adobe verifica cada ocorrência para ver se corresponde às regras de bot configuradas pela sua organização. Se uma determinada ocorrência corresponder a uma regra de bot, a ocorrência será excluída do relatório e essa métrica aumentará em um. Essa métrica inclui ambas as exibições de página ([`t()`](/help/implement/vars/functions/t-method.md)) e ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)), enquanto [Exibições de página de bot](bot-page-views.md) não inclua ocorrências de rastreamento de link.
