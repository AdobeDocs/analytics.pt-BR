---
title: Saídas
description: Um exemplo do último valor em uma visita.
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '186'
ht-degree: 100%

---

# Saídas

*Esta página de ajuda descreve como as saídas funcionam como uma métrica. Para obter informações sobre como as saídas funcionam como uma dimensão, consulte [Dimensões de Saída](../dimensions/exit-dimensions.md).*

A métrica “Saída” mostra o número de vezes que um determinado valor é registrado como o último valor em uma visita. Essa métrica ajuda a entender melhor sobre a última coisa que os visitantes veem antes de sair do site. Ver os últimos valores de uma dimensão pode ajudar a entender e otimizar a experiência que um visitante recebe antes de sair.

## Como essa métrica é calculada

Depois que uma [visita](visits.md) for concluída, registre o item de dimensão mais recente como uma saída. Existe apenas uma saída por dimensão por visita. Não é necessariamente a última ocorrência da visita se a dimensão foi definida em ocorrências anteriores. É uma métrica com base em visitas; ela se aplica retroativamente a todas as ocorrências na visita.

>[!TIP]
>
>Se essa métrica for visualizada em relação a uma dimensão que nem sempre está definida para todas as visitas, é possível ocultar o item de dimensão “Não especificado” no Analysis Workspace. Clique no ícone de filtro e desmarque [!UICONTROL Incluir não especificado (nenhum)].
