---
title: Entradas
description: Uma instância do primeiro valor em uma visita.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 1%

---


# Entradas

*Esta página de ajuda descreve como as entradas funcionam como uma métrica. Para obter informações sobre como as entradas funcionam como uma dimensão, consulte Dimensões[](../dimensions/entry-dimensions.md)de entrada.*

A métrica &#39;Entradas&#39; mostra o número de vezes que um determinado valor de dimensão é capturado como o primeiro valor em uma visita. Essa métrica é útil quando você deseja entender mais sobre as primeiras impressões que os visitantes têm no seu site. Ver os primeiros valores de uma dimensão pode ajudá-lo a entender e otimizar a experiência que um novo visitante obtém.

## Como essa métrica é calculada

Para uma determinada dimensão, registre o primeiro valor de dimensão visto em uma visita como uma entrada. Há apenas uma entrada por dimensão por visita. Não é necessariamente a primeira ocorrência da visita se a dimensão não estiver definida inicialmente. É uma métrica baseada em visitas; uma vez vinculado a um valor de dimensão, ele persistirá para o restante da visita.

>[!TIP]
>
>Se você visualização essa métrica em relação a uma dimensão nem sempre definida em cada visita, é possível ocultar o valor da dimensão &quot;Não especificado&quot; no Analysis Workspace. Clique no ícone de filtro e desmarque [!UICONTROL Incluir não especificado (Nenhum)].
