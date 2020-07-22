---
title: Número da visita
description: A nona visita do visitante.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 0%

---


# Número da visita

Os relatórios de dimensão &quot;Número de visita&quot; que visitam o visitante estão atualmente em. Quando uma nova visita é start, esse item de dimensão aumenta em uma unidade. Essa dimensão é útil quando você deseja entender como os visitantes estão envolvidos ao retornar ao seu site. É uma dimensão baseada em visita, o que significa que ela contém o mesmo valor para toda a visita e não pode ser alterada. Aplica-se à duração do visitante, independentemente do intervalo de datas do projeto.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios contiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem a string `"Visit number"` seguida pela representação numérica da visita em que o visitante está. Por exemplo, se o visitante nunca esteve em seu site antes, sua primeira visita pertence ao item de dimensão `"Visit number 1"`. Se esta for a 13ª visita do visitante ao seu site, ele pertencerá ao item de dimensão `"Visit number 13"`.
