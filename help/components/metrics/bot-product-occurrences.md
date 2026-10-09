---
title: Ocorrências de produto de bot
description: A métrica "Ocorrências de produto de bot" mostra o número de subocorrências de cadeias de caracteres de produtos que corresponderam às regras de bot e foram excluídas dos relatórios do Analytics.
feature: Metrics
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 7a99ecd99a9b1a639c8a2d48dc35d57fdfeb1a12
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 5%
---
# Ocorrências de produto de bot

A [métrica](overview.md) de &#39;Ocorrências de produto de bot&#39; mostra o número de sub-ocorrências que corresponderam às [Regras de bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Como o relatório de bot é separado do restante dos dados do conjunto de relatórios, essa métrica funciona somente com as seguintes dimensões:

* [Nome do bot](../dimensions/bot-name.md)
* Dimensões com base em tempo (por exemplo, [Dia](../dimensions/day.md), [Semana](../dimensions/week.md) ou [Mês](../dimensions/month.md))

Usar qualquer outra dimensão com essa métrica não retorna dados.

## Como essa métrica é calculada

O Adobe verifica cada sub-ocorrência com a [cadeia de caracteres do produto](/help/implement/vars/page-vars/products.md) para ver se ela corresponde às regras de bot configuradas pela sua organização. Se uma determinada sub-ocorrência corresponder a uma regra de bot, a sub-ocorrência será excluída do relatório e essa métrica aumentará em um.
