---
title: AM/PM
description: Determina se a ocorrência ocorreu durante as horas AM ou PM.
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 3%

---


# AM/PM

A dimensão &#39;AM/PM&#39; fornece informações sobre se a ocorrência ocorreu durante as horas AM ou PM. The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão funciona de forma ininterrupta. Ele não tem nenhuma configuração para alterar. Sua única dependência está no fuso horário do conjunto de relatórios, que determina quais horas são AM e quais são PM.

## Valores de dimensão

Essa dimensão sempre contém exatamente dois valores de dimensão: `"AM"` e `"PM"`. O valor da dimensão `"AM"` `"PM"` se aplica a todas as ocorrências de 12:00 AM a 11:59 AM, enquanto o valor da dimensão se aplica a todas as ocorrências de 12:00 PM a 11:59 PM.
