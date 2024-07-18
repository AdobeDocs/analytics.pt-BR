---
title: Saídas
description: Um exemplo do último valor em uma visita.
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 88%

---

# Saídas

*Esta página de ajuda descreve como as saídas funcionam como uma métrica. Para obter informações sobre como as saídas funcionam como uma dimensão, consulte [Dimensões de Saída](../dimensions/exit-dimensions.md).*

A [métrica](overview.md) de &quot;Saídas&quot; mostra o número de vezes que um determinado item de dimensão é capturado como o último valor em uma visita. Essa métrica ajuda a entender melhor sobre a última coisa que os visitantes veem antes de sair do site. Ver os últimos valores de uma dimensão pode ajudar a entender e otimizar a experiência que um visitante recebe antes de sair.

## Como essa métrica é calculada

Depois que uma [visita](visits.md) for concluída, registre o item de dimensão mais recente como uma saída. Existe apenas uma saída por dimensão por visita. Não é necessariamente a última ocorrência da visita se a dimensão foi definida em ocorrências anteriores. É uma métrica com base em visitas; ela se aplica retroativamente a todas as ocorrências na visita.

>[!TIP]
>
>Se essa métrica for visualizada em relação a uma dimensão que nem sempre está definida para todas as visitas, é possível ocultar o item de dimensão “Não especificado” no Analysis Workspace. Clique no ícone de filtro e desmarque [!UICONTROL Incluir não especificado (nenhum)].
