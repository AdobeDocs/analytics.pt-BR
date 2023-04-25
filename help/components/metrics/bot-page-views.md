---
title: Exibições da página de bot
description: O número de exibições de página que corresponderam às regras de bot.
source-git-commit: 61a0292bf2f8ff22b414c2e91da476c1da69d163
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 4%

---

# Exibições da página de bot

A métrica &quot;Visualizações de página de bot&quot; mostra o número de ocorrências de página que corresponderam [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Como os relatórios de bot são separados do restante dos dados do conjunto de relatórios, essa métrica só funciona com as seguintes dimensões:

* [Nome do bot](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensões baseadas em tempo (por exemplo, [Dia](../dimensions/day.md), [Semana](../dimensions/week.md)ou [Mês](../dimensions/month.md))

Usar qualquer outra dimensão com essa métrica não retorna dados.

## Como essa métrica é calculada

O Adobe verifica cada ocorrência de página para ver se corresponde às regras de bot que sua organização configurou. Se uma determinada ocorrência corresponder a uma regra de bot, a ocorrência da página será excluída do relatório e essa métrica aumentará em uma. Essa métrica não inclui ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).
