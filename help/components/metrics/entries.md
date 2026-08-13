---
title: Entradas
description: Uma instância do primeiro valor em uma visita.
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
TQID: https://experienceleague.adobe.com/H3LE0wm2uDL3-pILbvOXvccAJQdo5o9X3uHJ4xZe7UU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 89%

---

# Entradas

*Esta página de ajuda descreve como as entradas funcionam como uma métrica. Para obter informações sobre como as entradas funcionam como uma dimensão, consulte [Dimensões de entrada](../dimensions/entry-dimensions.md).*

A [métrica](overview.md) de &quot;Entradas&quot; mostra o número de vezes que um determinado item de dimensão é capturado como o primeiro valor em uma visita. Essa métrica é útil para entender as primeiras impressões que os visitantes têm no site. Ver os primeiros valores de uma dimensão pode ajudar a entender e otimizar a experiência que um novo visitante tem.

## Como essa métrica é calculada

Para uma determinada dimensão, registre o primeiro item de dimensão visto em uma visita como uma entrada. Existe apenas uma entrada por dimensão por visita. Não é necessariamente a última ocorrência da visita se a dimensão não estiver definida inicialmente. É uma métrica baseada em visitas; uma vez vinculada a um item de dimensão, ela persistirá no restante da visita.

>[!TIP]
>
>Se essa métrica for visualizada em relação a uma dimensão que nem sempre está definida para todas as visitas, é possível ocultar o item de dimensão “Não especificado” no Analysis Workspace. Clique no ícone de filtro e desmarque [!UICONTROL Incluir não especificado (nenhum)].
