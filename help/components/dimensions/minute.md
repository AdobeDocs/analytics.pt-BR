---
title: Minuto
description: O minuto em que a métrica ocorreu.
translation-type: tm+mt
source-git-commit: 2c262e5345c39a71a6a54062c607273528294b24
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 1%

---


# Minuto

A dimensão &#39;Minuto&#39; relata o minuto em que uma determinada métrica ocorreu (arredondada para baixo). O primeiro valor de dimensão é o primeiro minuto no intervalo de datas, e o último valor de dimensão é o último minuto no intervalo de datas. Essa dimensão é valiosa para relatórios de tendências, pois permite que você visualize métricas ao longo do tempo. Dada a grandeza dessa dimensão, a Adobe recomenda limitar o intervalo de datas do relatórios a um ou dois dias.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios contiver dados, essa dimensão funcionará.

## Valores de dimensão

Os valores de dimensão incluem um determinado minuto dentro do intervalo de datas de um relatório ao lado de sua data. É formatado como `HH:MM YYYY-MM-DD`. Valores de dimensão que começam com `00:00` igual a meia-noite nesse dia, enquanto valores que começam com `23:59` igual a 11:59 PM para esse dia.
