---
title: Saídas
description: Uma instância do último valor em uma visita.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---


# Saídas

*Esta página de ajuda descreve como as saídas funcionam como uma métrica. Para obter informações sobre como as saídas funcionam como uma dimensão, consulte Dimensões[de](../dimensions/exit-dimensions.md)saída.*

A métrica &quot;Saídas&quot; mostra o número de vezes que um determinado valor de dimensão é capturado como o último valor em uma visita. Essa métrica é útil quando você deseja entender mais sobre a última coisa que os visitantes veem antes de sair do site. Ver os últimos valores de uma dimensão pode ajudá-lo a entender e otimizar a experiência que um visitante recebe antes de sair.

## Como essa métrica é calculada

Depois que uma [visita](visits.md) for concluída, registre o valor de dimensão mais recente como uma saída. Existe apenas uma saída por dimensão por visita. Não é necessariamente a última ocorrência da visita se a dimensão foi definida em ocorrências anteriores. É uma métrica baseada em visitas; aplica-se retroativamente a todas as ocorrências na visita.

>[!TIP]
>
>Se você visualização essa métrica em relação a uma dimensão nem sempre definida em cada visita, é possível ocultar o valor da dimensão &quot;Não especificado&quot; no Analysis Workspace. Clique no ícone de filtro e desmarque [!UICONTROL Incluir não especificado (Nenhum)].
