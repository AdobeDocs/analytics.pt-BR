---
title: Exibições de página de bot
description: O número de exibições de página que corresponderam às regras de bot.
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 11%

---

# Exibições de página de bot

A [métrica](overview.md) de &#39;Exibições de página de bot&#39; mostra o número de ocorrências de página que corresponderam às [Regras de bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Como o relatório de bot é separado do restante dos dados do conjunto de relatórios, essa métrica funciona somente com as seguintes dimensões:

* [Nome do bot ](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensões com base em tempo (por exemplo, [Dia](../dimensions/day.md), [Semana](../dimensions/week.md) ou [Mês](../dimensions/month.md))

Usar qualquer outra dimensão com essa métrica não retorna dados.

## Como essa métrica é calculada

O Adobe verifica cada ocorrência de página para ver se corresponde às regras de bot configuradas pela sua organização. Se uma determinada ocorrência corresponder a uma regra de bot, a ocorrência da página será excluída do relatório e essa métrica aumentará em um. Essa métrica não inclui ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).
