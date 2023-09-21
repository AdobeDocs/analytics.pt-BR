---
title: Hora do dia
description: A hora numérica do dia, independentemente do dia.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 95%

---

# Hora do dia

A &#39;Hora do dia&#39; [dimension](overview.md) relata a hora numérica de qualquer dia como um item de dimensão. Por exemplo, se você tiver um relatório que abrange de 1º de janeiro a 7 de janeiro, a primeira hora de cada dia será agrupada no mesmo item de dimensão. Esse relatório é importante se você quiser que um relatório seja dividido por hora relativa do dia, mas não quiser horas estáticas como itens de dimensão. Ela é especialmente valiosa como uma dimensão em relatórios programados, já que essa dimensão é acumulada com o intervalo de datas selecionado.

Essa dimensão se baseia no fuso horário do conjunto de relatórios, e não no fuso horário local do visitante. Por exemplo, se o seu conjunto de relatórios estiver no Horário da Montanha e um visitante da Califórnia visitar seu site às 10h da manhã, no horário do Pacífico, a ocorrência é agrupada abaixo do item de dimensão `11:00 AM`. Se você quiser uma dimensão que registre o tempo do visitante local, a Adobe recomenda usar o plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem `12:00 AM` - `11:00 PM`, representando a hora do dia em que a ocorrência aconteceu (arredondada para baixo). Por exemplo, se uma ocorrência foi gerada às 15h58, ela se agrupa no item de dimensão `3:00 PM`.

## Horário de verão

O horário de verão é uma prática em que os relógios são adiantados uma hora na primavera e atrasados uma hora no outono. Se o fuso horário de um conjunto de relatórios usar horário de verão, a Adobe ajusta os dados de acordo com essa hora.

* **Quando o horário de verão começar**: em março, os relatórios geralmente mostram um intervalo de uma hora nos dados em que o horário de verão começa. A hora não existia, portanto, não faz parte da coleção de dados. Observe que uma pequena quantidade de dados ainda pode chegar a essa hora. Os servidores de coleção de dados da Adobe levam vários segundos (até um minuto) para considerar os ajustes de horário de verão.
* **Quando o horário de verão terminar**: em novembro, os relatórios geralmente mostram uma hora dupla em que o horário de verão termina. A hora aconteceu duas vezes, então ambas as horas são agregadas nos relatórios.
