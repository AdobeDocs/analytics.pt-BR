---
title: Entradas
description: Uma instância do primeiro valor em uma visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 57%

---


# Entradas

*Esta página de ajuda descreve como as entradas funcionam como uma métrica. Para obter informações sobre como as entradas funcionam como uma dimensão, consulte[Dimensões de entrada](../dimensions/entry-dimensions.md).*

A métrica &#39;Entradas&#39; mostra o número de vezes que um determinado item de dimensão é capturado como o primeiro valor em uma visita. Essa métrica é útil para entender as primeiras impressões que os visitantes têm no site. Ver os primeiros valores de uma dimensão pode ajudar a entender e otimizar a experiência que um novo visitante tem.

## Como essa métrica é calculada

Para uma determinada dimensão, registre o primeiro item de dimensão visto em uma visita como uma entrada. Existe apenas uma entrada por dimensão por visita. Não é necessariamente a última ocorrência da visita se a dimensão não estiver definida inicialmente. É uma métrica baseada em visitas; uma vez vinculado a um item de dimensão, ele persiste para o restante da visita.

>[!TIP]
>
>Se você visualização essa métrica em relação a uma dimensão nem sempre definida em cada visita, é possível ocultar o item de dimensão &quot;Não especificado&quot; no Analysis Workspace. Clique no ícone de filtro e desmarque [!UICONTROL Incluir não especificado (nenhum)].
