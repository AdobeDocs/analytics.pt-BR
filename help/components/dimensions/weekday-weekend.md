---
title: Dia da semana/Fim de semana
description: Determina se a ocorrência ocorreu durante um dia da semana ou um fim de semana.
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 3%

---


# Dia da semana/Fim de semana

A dimensão &#39;Dia da semana/Fim de semana&#39; fornece informações sobre se a ocorrência aconteceu durante um dia da semana (de segunda a sexta-feira) ou fim de semana (sábado a domingo). The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios contiver dados, essa dimensão funcionará.

## Valores de dimensão

Essa dimensão sempre contém exatamente dois valores de dimensão: `"Weekday"` e `"Weekend"`. O valor da dimensão `"Weekday"` se aplica a todas as ocorrências de segunda a sexta-feira, enquanto o valor da dimensão `"Weekend"` se aplica a todas as ocorrências de sábado e domingo.
