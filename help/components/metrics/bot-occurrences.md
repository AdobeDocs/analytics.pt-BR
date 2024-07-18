---
title: Ocorrências de bot
description: O número de ocorrências que corresponderam às regras de bot.
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# Ocorrências de bot

A [métrica](overview.md) de &#39;Ocorrências de bot&#39; mostra o número de ocorrências que corresponderam às [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Como o relatório de bot é separado do restante dos dados do conjunto de relatórios, essa métrica funciona somente com as seguintes dimensões:

* [Nome do bot ](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensões com base em tempo (por exemplo, [Dia](../dimensions/day.md), [Semana](../dimensions/week.md) ou [Mês](../dimensions/month.md))

Usar qualquer outra dimensão com essa métrica não retorna dados.

## Como essa métrica é calculada

O Adobe verifica cada ocorrência para ver se corresponde às regras de bot configuradas pela sua organização. Se uma determinada ocorrência corresponder a uma regra de bot, a ocorrência será excluída do relatório e essa métrica aumentará em um. Essa métrica inclui exibições de página ([`t()`](/help/implement/vars/functions/t-method.md)) e ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)), enquanto [Exibições de página de bot](bot-page-views.md) não incluem ocorrências de rastreamento de link.
