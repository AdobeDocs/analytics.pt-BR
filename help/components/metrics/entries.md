---
title: Entradas
description: Uma instância do primeiro valor em uma visita.
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%

---

# Entradas

*Esta página de ajuda descreve como as entradas funcionam como uma métrica. Para obter informações sobre como as entradas funcionam como uma dimensão, consulte [Dimensões de entrada](../dimensions/entry-dimensions.md).*

A métrica “Entrada” exibe o número de vezes que um determinado item de dimensão é registrado como o primeiro em uma visita. Essa métrica é útil para entender as primeiras impressões que os visitantes têm no site. Ver os primeiros valores de uma dimensão pode ajudar a entender e otimizar a experiência que um novo visitante tem.

## Como essa métrica é calculada

Para uma determinada dimensão, registre o primeiro item de dimensão visto em uma visita como uma entrada. Existe apenas uma entrada por dimensão por visita. Não é necessariamente a última ocorrência da visita se a dimensão não estiver definida inicialmente. É uma métrica baseada em visitas; uma vez vinculada a um item de dimensão, ela persistirá no restante da visita.

>[!TIP]
>
>Se essa métrica for visualizada em relação a uma dimensão que nem sempre está definida para todas as visitas, é possível ocultar o item de dimensão “Não especificado” no Analysis Workspace. Clique no ícone de filtro e desmarque [!UICONTROL Incluir não especificado (nenhum)].
