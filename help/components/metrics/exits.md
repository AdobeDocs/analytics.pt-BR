---
title: Saídas
description: Um exemplo do último valor em uma visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 68%

---


# Saídas

*Esta página de ajuda descreve como as saídas funcionam como uma métrica. Para obter informações sobre como as saídas funcionam como uma dimensão, consulte[Dimensões de Saída](../dimensions/exit-dimensions.md).*

A métrica &quot;Saídas&quot; mostra o número de vezes que um determinado item de dimensão é capturado como o último valor em uma visita. Essa métrica ajuda a entender melhor sobre a última coisa que os visitantes veem antes de sair do site. Ver os últimos valores de uma dimensão pode ajudar a entender e otimizar a experiência que um visitante recebe antes de sair.

## Como essa métrica é calculada

After a [visit](visits.md) concludes, record the most recent dimension item as an exit. Existe apenas uma saída por dimensão por visita. Não é necessariamente a última ocorrência da visita se a dimensão foi definida em ocorrências anteriores. É uma métrica com base em visitas; ela se aplica retroativamente a todas as ocorrências na visita.

>[!TIP]
>
>Se você visualização essa métrica em relação a uma dimensão nem sempre definida em cada visita, é possível ocultar o item de dimensão &quot;Não especificado&quot; no Analysis Workspace. Clique no ícone de filtro e desmarque [!UICONTROL Incluir não especificado (nenhum)].
