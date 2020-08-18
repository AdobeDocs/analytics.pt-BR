---
title: Hora
description: A hora em que a métrica ocorreu.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 10%

---


# Hora

A dimensão &#39;Hora&#39; relata a hora em que uma determinada métrica ocorreu (arredondada para baixo). O primeiro item de dimensão é a primeira hora no intervalo de datas, e o último item de dimensão é a última hora no intervalo de datas. Essa dimensão é valiosa para relatórios de tendências, pois permite que você visualize métricas ao longo do tempo.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## itens de Dimension

Os itens de Dimension incluem uma determinada hora dentro do intervalo de datas de um relatório ao lado de sua data. É formatado como `HH:HH YYYY-MM-DD`.

## Horário de verão

O Horário de Verão é uma prática em que os relógios são colocados uma hora à frente na primavera e devolvidos uma hora no outono. Se o fuso horário de um conjunto de relatórios usar DST, o Adobe ajusta os dados de acordo com essa hora.

* **Quando o horário de verão começar**: Em março, os relatórios normalmente mostram um intervalo de uma hora nos dados em que os start de horário de verão. A hora não existia, portanto, não faz parte da coleta de dados. Observe que uma pequena quantidade de dados ainda pode chegar a essa hora. Os servidores de coleta de dados de Adobe levam vários segundos (até um minuto) para levar em conta os ajustes de DST.
* **Quando o Horário de verão terminar**: Em novembro, os relatórios normalmente mostram uma hora empilhada em duplo, onde o Horário de verão termina. A hora aconteceu duas vezes, então ambas as horas são agregadas nos relatórios.
