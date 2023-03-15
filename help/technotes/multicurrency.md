---
description: Descreve como definir códigos monetários de destino para que o suporte a várias moedas funcione.
title: Suporte a várias moedas
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 10%

---

# Suporte a várias moedas

O Adobe oferece vários níveis de conversão de moeda para que sua organização possa alcançar a moeda desejada em muitos relatórios. Ocorre uma conversão em três níveis:

## Nível da página

Você pode usar o [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) para definir a moeda desejada em cada página. Se a moeda na página não corresponder à moeda do conjunto de relatórios de destino, o Adobe executará uma conversão de moeda para a moeda do conjunto de relatórios com base na taxa de câmbio do dia. A moeda convertida é registrada.

## Nível do conjunto de relatórios

Todo conjunto de relatórios tem um **moeda de base**. Essa moeda determina o contexto de todas as métricas de moeda (como [Receita](/help/components/metrics/revenue.md)). Todos os dados de moeda armazenados estão na moeda base do conjunto de relatórios.

## Nível do usuário

Para o Reports &amp; Analytics, os usuários podem definir uma moeda diferente da moeda base do conjunto de relatórios em [Configurações do relatório](/help/analyze/reports-analytics/report-settings.md). Essa configuração não é destrutiva, o que significa que não altera os dados subjacentes. Em vez disso, ela aplica uma conversão básica de moeda a todos os relatórios exibidos com base na taxa de câmbio atual. Se você exibir o mesmo relatório em dias diferentes, os números poderão ser alterados devido a diferentes taxas de câmbio diárias.

Atualmente, o Analysis Workspace não oferece conversão de moeda no nível do usuário.
