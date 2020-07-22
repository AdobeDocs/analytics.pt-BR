---
title: AM/PM
description: Determina se a ocorrência ocorreu durante as horas AM ou PM.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 3%

---


# AM/PM

A dimensão &#39;AM/PM&#39; fornece informações sobre se a ocorrência ocorreu durante as horas AM ou PM. The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão funciona de forma ininterrupta. Ele não tem nenhuma configuração para alterar. Sua única dependência está no fuso horário do conjunto de relatórios, que determina quais horas são AM e quais são PM.

## Itens de dimensão

Essa dimensão sempre contém exatamente dois itens de dimensão: `"AM"` e `"PM"`. O item de dimensão `"AM"` se aplica a todas as ocorrências das 12:00 às 11:59 AM, enquanto o item de dimensão se `"PM"` aplica a todas as ocorrências das 12:00 às 11:59.
