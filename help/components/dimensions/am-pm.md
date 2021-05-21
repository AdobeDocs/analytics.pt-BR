---
title: AM/PM
description: Determina se a ocorrência aconteceu durante as horas AM ou PM.
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '117'
ht-degree: 100%

---

# AM/PM

A dimensão “AM/PM” fornece informações sobre se a ocorrência aconteceu durante as horas AM ou PM. O horário da ocorrência tem como base o [fuso horário do conjunto de relatórios](/help/admin/admin/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente. Nenhuma configuração precisa ser alterada. Sua única dependência está no fuso horário do conjunto de relatórios, que determina quais horas são AM e quais são PM.

## Itens de dimensão

Essa dimensão sempre contém exatamente dois itens de dimensão: `"AM"` e `"PM"`. O item de dimensão `"AM"` se aplica a todas as ocorrências de 12:00 AM às 11:59 AM, enquanto o item de dimensão `"PM"` se aplica a todas as ocorrências de 12:00 PM às 11:59 PM.
