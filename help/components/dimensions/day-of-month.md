---
title: Dia do mês
description: O dia numérico do mês, independentemente de qual mês.
feature: Dimensions
exl-id: 6d27aa9f-ce75-4a27-bb92-3acabe3975a1
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 100%

---

# Dia do mês

A dimensão “Dia do mês” informa o dia numérico de qualquer mês como um item de dimensão. Por exemplo, se você tiver um relatório que vai de 1º de janeiro a 31 de março, o primeiro dia de cada mês se agrupará no mesmo item de dimensão. Esse relatório é importante se você quiser que um relatório seja dividido pelo dia, mas não quiser uma data estática como itens de dimensão. Ela é especialmente valiosa como uma dimensão em relatórios programados, já que essa dimensão é acumulada com o intervalo de datas selecionado.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem os números `1` - `31`, representando o dia do mês em que a ocorrência aconteceu.
