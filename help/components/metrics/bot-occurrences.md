---
title: Ocorrências de bot
description: O número de ocorrências que corresponderam às regras de bot.
feature: Metrics
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 4%

---

# Ocorrências de bot

A métrica &quot;Ocorrências de bot&quot; mostra o número de ocorrências correspondentes [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Como o relatório de bot é separado do restante dos dados do conjunto de relatórios, essa métrica funciona somente com as seguintes dimensões:

* [Nome do bot](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensões com base no tempo (por exemplo, [Dia](../dimensions/day.md), [Semana](../dimensions/week.md)ou [Month](../dimensions/month.md))

Usar qualquer outra dimensão com essa métrica não retorna dados.

## Como essa métrica é calculada

O Adobe verifica cada ocorrência para ver se corresponde às regras de bot configuradas pela sua organização. Se uma determinada ocorrência corresponder a uma regra de bot, a ocorrência será excluída do relatório e essa métrica aumentará em um. Essa métrica inclui ambas as exibições de página ([`t()`](/help/implement/vars/functions/t-method.md)) e ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)), enquanto [Exibições de página de bot](bot-page-views.md) não inclua ocorrências de rastreamento de link.
