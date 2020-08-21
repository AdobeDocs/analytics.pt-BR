---
title: Dia da semana/Fim de semana
description: Determina se a ocorrência ocorreu durante um dia da semana ou um fim de semana.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 68%

---


# Dia da semana/Fim de semana

A dimensão “Dia da semana/Fim de semana” fornece insight sobre o período em que a ocorrência aconteceu, se foi durante um dia da semana (de segunda a sexta-feira) ou no fim de semana (sábado a domingo). O horário da ocorrência tem como base o [fuso horário do conjunto de relatórios](/help/admin/admin/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## itens de Dimension

This dimension always contains exactly two dimension items: `"Weekday"` and `"Weekend"`. The dimension item `"Weekday"` applies to all hits Monday through Friday, while the dimension item `"Weekend"` applies to all hits on Saturday and Sunday.
