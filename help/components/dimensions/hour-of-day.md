---
title: Hora do dia
description: A hora numérica do dia, independentemente do dia.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 8%

---


# Hora do dia

A dimensão &#39;Hora do dia&#39; relata a hora numérica de qualquer dia como um item de dimensão. Por exemplo, se você tiver um relatório que abrange de 1 de janeiro a 7 de janeiro, a primeira hora de cada dia será agrupada no mesmo item de dimensão. Este relatório é importante se você quiser que um relatório seja detalhado por hora relativa do dia, mas não quiser horas estáticas como itens de dimensão. Ela é especialmente valiosa como uma dimensão em relatórios programados, já que essa dimensão é acumulada com o intervalo de datas selecionado.

Essa dimensão se baseia no fuso horário do conjunto de relatórios, e não no fuso horário local do visitante. Por exemplo, se seu conjunto de relatórios estiver em Hora de Montanha e um visitante na Califórnia visitar seu site às 10:00 da manhã, horário do Pacífico, os grupos de ocorrência abaixo do item de `11:00 AM` dimensão. Se você quiser uma dimensão que registre o tempo do visitante local, o Adobe recomenda o uso do plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) .

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## itens de Dimension

Os itens de Dimension incluem `12:00 AM` - `11:00 PM`, representando a hora do dia em que a ocorrência ocorreu (arredondada para baixo). Por exemplo, se uma ocorrência foi gerada às 15:58, ela se agrupa no item de dimensão de `3:00 PM`.

## Horário de verão

O Horário de Verão é uma prática em que os relógios são colocados uma hora à frente na primavera e devolvidos uma hora no outono. Se o fuso horário de um conjunto de relatórios usar DST, o Adobe ajusta os dados de acordo com essa hora.

* **Quando o horário de verão começar**: Em março, os relatórios normalmente mostram um intervalo de uma hora nos dados em que os start de horário de verão. A hora não existia, portanto, não faz parte da coleta de dados. Observe que uma pequena quantidade de dados ainda pode chegar a essa hora. Os servidores de coleta de dados de Adobe levam vários segundos (até um minuto) para levar em conta os ajustes de DST.
* **Quando o Horário de verão terminar**: Em novembro, os relatórios normalmente mostram uma hora empilhada em duplo, onde o Horário de verão termina. A hora aconteceu duas vezes, então ambas as horas são agregadas nos relatórios.
