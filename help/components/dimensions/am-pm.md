---
title: AM/PM
description: Determina se a ocorrência aconteceu durante as horas AM ou PM.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 70%

---


# AM/PM

A dimensão “AM/PM” fornece informações sobre se a ocorrência aconteceu durante as horas AM ou PM. O horário da ocorrência tem como base o [fuso horário do conjunto de relatórios](/help/admin/admin/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente. Nenhuma configuração precisa ser alterada. Sua única dependência está no fuso horário do conjunto de relatórios, que determina quais horas são AM e quais são PM.

## itens de Dimension

This dimension always contains exactly two dimension items: `"AM"` and `"PM"`. The dimension item `"AM"` applies to all hits from 12:00 AM to 11:59 AM, while the dimension item `"PM"` applies to all hits from 12:00 PM to 11:59 PM.
