---
title: Dia da semana/Fim de semana
description: Determina se a ocorrência ocorreu durante um dia da semana ou um fim de semana.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '105'
ht-degree: 100%

---


# Dia da semana/Fim de semana

A dimensão “Dia da semana/Fim de semana” fornece insight sobre o período em que a ocorrência aconteceu, se foi durante um dia da semana (de segunda a sexta-feira) ou no fim de semana (sábado a domingo). O horário da ocorrência tem como base o [fuso horário do conjunto de relatórios](/help/admin/admin/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Essa dimensão sempre contém exatamente dois itens de dimensão: `"Weekday"` e `"Weekend"`. O item de dimensão `"Weekday"` se aplica a todas as ocorrências de segunda a sexta-feira, enquanto o item de dimensão `"Weekend"` se aplica a todas as ocorrências de sábado e domingo.
