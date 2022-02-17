---
title: Dia da semana/Fim de semana
description: Determina se a ocorrência ocorreu durante um dia da semana ou um fim de semana.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 100%

---

# Dia da semana/Fim de semana

A dimensão “Dia da semana/Fim de semana” fornece insight sobre o período em que a ocorrência aconteceu, se foi durante um dia da semana (de segunda a sexta-feira) ou no fim de semana (sábado a domingo). O horário da ocorrência tem como base o [fuso horário do conjunto de relatórios](/help/admin/admin/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Essa dimensão sempre contém exatamente dois itens de dimensão: `"Weekday"` e `"Weekend"`. O item de dimensão `"Weekday"` se aplica a todas as ocorrências de segunda a sexta-feira, enquanto o item de dimensão `"Weekend"` se aplica a todas as ocorrências de sábado e domingo.
