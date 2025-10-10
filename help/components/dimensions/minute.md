---
title: Minuto
description: O minuto em que a métrica ocorreu.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 76%

---

# Minuto

O &#39;Minuto&#39; [dimensão](overview.md) informa o minuto em que uma determinada métrica ocorreu (arredondado para baixo). O primeiro item de dimensão é o primeiro minuto no intervalo de datas, e o último item de dimensão é o último minuto no intervalo de datas. Essa dimensão é importante para os relatórios de tendências, pois permite visualizar métricas ao longo do tempo. Dada a grandeza dessa dimensão, a Adobe recomenda limitar o intervalo de datas dos relatórios a um ou dois dias.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem um determinado minuto dentro do intervalo de datas de um relatório ao lado de sua data. É formatado como `HH:MM YYYY-MM-DD`. Itens de Dimension que começam com `00:00` são iguais a meia-noite nesse dia, enquanto valores que começam com `23:59` são iguais a 23h :59 para aquele dia.
