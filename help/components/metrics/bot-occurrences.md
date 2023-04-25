---
title: Ocorrências de bot
description: O número de ocorrências que corresponderam às regras de bot.
source-git-commit: 61a0292bf2f8ff22b414c2e91da476c1da69d163
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 4%

---

# Ocorrências de bot

A métrica &quot;Ocorrências de bot&quot; mostra o número de ocorrências que corresponderam [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Como os relatórios de bot são separados do restante dos dados do conjunto de relatórios, essa métrica só funciona com as seguintes dimensões:

* [Nome do bot](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensões baseadas em tempo (por exemplo, [Dia](../dimensions/day.md), [Semana](../dimensions/week.md)ou [Mês](../dimensions/month.md))

Usar qualquer outra dimensão com essa métrica não retorna dados.

## Como essa métrica é calculada

O Adobe verifica cada ocorrência para ver se corresponde às regras de bot que sua organização configurou. Se uma determinada ocorrência corresponder a uma regra de bot, a ocorrência será excluída do relatório e essa métrica aumentará em uma. Essa métrica inclui ambas as exibições de página ([`t()`](/help/implement/vars/functions/t-method.md)) e ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)), [Exibições da página de bot](bot-page-views.md) não inclua ocorrências de rastreamento de link.
