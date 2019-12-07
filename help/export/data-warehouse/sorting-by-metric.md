---
description: Oferece relatórios classificados e detalhados no Data Warehouse, organizados pelo valor de métrica decrescente.
title: Classificar por métrica
uuid: 07da2607-b3fd-463b-90d4-6884a93c7e25
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Classificar por métrica

Oferece relatórios classificados e detalhados no Data Warehouse, organizados pelo valor de métrica decrescente.

A classificação por métrica facilita a interpretação dos relatórios do Data Warehouse, além de facilitar a comparação deles com outros relatórios de exibição de detalhamento do Analytics.

Abaixo, você verá como ocorre a reorganização de linhas de um relatório do Data Warehouse por meio da ativação da opção “Classificação de métricas”.

Há quatro maneiras de organizar os relatórios do Data Warehouse com a “Classificação de métricas”, com base em como foram configurados a granularidade de data, dimensões de relatórios ou métricas, e se “Linhas máximas” foi definido:

* **Layout 1**: os itens da linha são organizados em ordem alfabética (padrão). Se “Linhas máximas” estiver definido, somente as primeiras N linhas serão incluídas no relatório.
* **Layout 2**: o Data Warehouse aplica uma classificação de métrica em todas as linhas do relatório. Resultados iguais no primeiro valor de métrica são detalhados pela segunda métrica, e então pela terceira, e assim por diante. No caso de todas as métricas coincidirem, é aplicada a ordem alfabética padrão de detalhamento de itens de linha.
* **Layout 3**: similar ao Layout 2, entretanto, somente as N linhas superiores (ou seja, o número definido em “linhas máximas”) são exibidas no relatório.
* **Layout 4**: similar ao Layout 2, com a exceção de que os itens de cada intervalo de granularidade de data são agrupados e classificados de acordo com os respectivos intervalos de data.

Consulte a coluna “Layout do relatório” nesta tabela para determinar como “Classificação de métricas” interage com outras opções de relatórios do Data Warehouse.

| Classificar por métrica? | Tem métricas? | Tem detalhamento? | Granularidade de data? | Conjunto máximo de linhas? | Layout do relatório |
|---|---|---|---|---|---|
| Não | Sim ou Não | Sim ou Não | Sim ou Não | Sim ou Não | 1 |
| Sim | Não | Sim ou Não | Sim ou Não | Sim ou Não | 1 |
| Sim | Sim | Não | Não | N/D | 1 |
| Sim | Sim | Não | Sim ou Não | Não | 1 |
| Sim | Sim | Sim | Não | Não | 2 |
| Sim | Sim | Não | Sim | Sim | 3 |
| Sim | Sim | Sim | Sim ou Não | Sim | 3 |
| Sim | Sim | Sim | Sim | Não | 4 |

