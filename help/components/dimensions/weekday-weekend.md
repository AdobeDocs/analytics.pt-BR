---
title: Dia da semana/Fim de semana
description: Determina se a ocorrência ocorreu durante um dia da semana ou um fim de semana.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 80%

---

# Dia da semana/Fim de semana

O &quot;Dia da semana/Fim de semana&quot; [dimension](overview.md) O fornece informações sobre se a ocorrência aconteceu durante um dia da semana (de segunda a sexta-feira) ou no fim de semana (sábado a domingo). O horário da ocorrência tem como base o [fuso horário do conjunto de relatórios](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Essa dimensão sempre contém exatamente dois itens de dimensão: `"Weekday"` e `"Weekend"`. O item de dimensão `"Weekday"` se aplica a todas as ocorrências de segunda a sexta-feira, enquanto o item de dimensão `"Weekend"` se aplica a todas as ocorrências de sábado e domingo.
