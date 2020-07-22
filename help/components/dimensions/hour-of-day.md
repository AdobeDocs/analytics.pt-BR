---
title: Hora do dia
description: A hora numérica do dia, independentemente do dia.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---


# Hora do dia

A dimensão &#39;Hora do dia&#39; relata a hora numérica de qualquer dia como um item de dimensão. Por exemplo, se você tiver um relatório que abrange de 1 de janeiro a 7 de janeiro, a primeira hora de cada dia será agrupada no mesmo item de dimensão. Este relatório é importante se você quiser que um relatório seja detalhado por hora relativa do dia, mas não quiser horas estáticas como itens de dimensão. Ela é especialmente valiosa como uma dimensão em relatórios programados, já que essa dimensão é acumulada com o intervalo de datas selecionado.

Essa dimensão se baseia no fuso horário do conjunto de relatórios, e não no fuso horário local do visitante. Por exemplo, se seu conjunto de relatórios estiver em Hora de Montanha e um visitante na Califórnia visitar seu site às 10:00 da manhã, horário do Pacífico, os grupos de ocorrência abaixo do item de `11:00 AM` dimensão. Se você quiser uma dimensão que registre o tempo do visitante local, a Adobe recomenda usar o plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) .

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios contiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem `12:00 AM` - `11:00 PM`, representando a hora do dia em que a ocorrência ocorreu (arredondada para baixo). Por exemplo, se uma ocorrência foi gerada às 15:58, ela se agrupa no item de dimensão de `3:00 PM`.
