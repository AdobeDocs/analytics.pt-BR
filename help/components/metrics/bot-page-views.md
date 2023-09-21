---
title: Exibições de página de bot
description: O número de exibições de página que corresponderam às regras de bot.
feature: Metrics
exl-id: 9b1efcb1-10ca-40fb-8f20-e6da105366d9
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 11%

---

# Exibições de página de bot

As &quot;Exibições de página de bot&quot; [métrica](overview.md) mostra o número de ocorrências de página correspondentes [Regras de bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Como o relatório de bot é separado do restante dos dados do conjunto de relatórios, essa métrica funciona somente com as seguintes dimensões:

* [Nome do bot ](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensões com base no tempo (por exemplo, [Dia](../dimensions/day.md), [Semana](../dimensions/week.md)ou [Month](../dimensions/month.md))

Usar qualquer outra dimensão com essa métrica não retorna dados.

## Como essa métrica é calculada

O Adobe verifica cada ocorrência de página para ver se corresponde às regras de bot configuradas pela sua organização. Se uma determinada ocorrência corresponder a uma regra de bot, a ocorrência da página será excluída do relatório e essa métrica aumentará em um. Essa métrica não inclui ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).
