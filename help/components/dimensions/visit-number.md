---
title: Número da visita
description: A nona visita do visitante.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 59%

---


# Número da visita

Os relatórios de dimensão &quot;Número de visita&quot; em que o visitante está atualmente. Quando uma nova visita é start, esse item de dimensão aumenta em uma unidade. Essa dimensão é útil quando você deseja entender como os visitantes estão envolvidos ao retornar ao seu site. É uma dimensão baseada em visita, o que significa que ela contém o mesmo valor para toda a visita e não pode ser alterada. Ela se aplica à duração do visitante, independentemente do intervalo de datas do projeto.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## itens de Dimension

Dimension items include the string `"Visit number"` followed by the numeric representation of the visit the visitor is currently on. For example, if the visitor has never been to your site before, their first visit belongs to the dimension item `"Visit number 1"`. If this is the visitor&#39;s 13th visit to your site, they belong to the dimension item `"Visit number 13"`.
