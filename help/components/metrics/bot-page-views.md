---
title: Exibições de página de bot
description: O número de exibições de página que corresponderam às regras de bot.
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
TQID: https://experienceleague.adobe.com/Y0r2fzF87dep4NsrbJGCC9OnqBHrZozCh2DovNc90KQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 125
ht-degree: 11%

---

# Exibições de página de bot

A [métrica](overview.md) de &#39;Exibições de página de bot&#39; mostra o número de ocorrências de página que corresponderam às [Regras de bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Como o relatório de bot é separado do restante dos dados do conjunto de relatórios, essa métrica funciona somente com as seguintes dimensões:

* [Nome do bot](../dimensions/bot-name.md)
* [Página](../dimensions/page.md)
* Dimensões com base em tempo (por exemplo, [Dia](../dimensions/day.md), [Semana](../dimensions/week.md) ou [Mês](../dimensions/month.md))

Usar qualquer outra dimensão com essa métrica não retorna dados.

## Como essa métrica é calculada

O Adobe verifica cada ocorrência de página para ver se corresponde às regras de bot configuradas pela sua organização. Se uma determinada ocorrência corresponder a uma regra de bot, a ocorrência da página será excluída do relatório e essa métrica aumentará em um. Essa métrica não inclui ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).
