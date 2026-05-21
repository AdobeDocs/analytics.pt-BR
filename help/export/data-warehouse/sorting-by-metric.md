---
description: Saiba como a classificação por métrica facilita a interpretação e a comparação dos relatórios do Data Warehouse com outras exibições de relatórios de detalhamento do Analytics.
title: Classificar por métrica
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
TQID: https://experienceleague.adobe.com/YPqL6i9RWACubLdf2ywm8xuPyeQkZ30L6rO6FAbhpJI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 337
ht-degree: 17%

---

# Classificar por métrica

Fornece relatórios classificados e detalhados no Data Warehouse, classificados por valor de métrica decrescente.

A classificação por métrica facilita a interpretação dos relatórios do Data Warehouse e a comparação desses relatórios com outras exibições de relatórios de detalhamento do Analytics.

A seguir, é mostrado como ativar a opção &quot;Classificação de métricas&quot; reorganizará as linhas em um relatório do Data Warehouse.

Há quatro maneiras possíveis para os relatórios do Data Warehouse serem organizados com &quot;Classificação de métricas&quot;, com base em como a granularidade da data, as dimensões de relatório ou as métricas são configuradas e se &quot;Máximo de linhas&quot; está definido:

* **Layout 1**: os itens de linha são classificados em ordem de dicionário (padrão). Se &quot;Máximo de linhas&quot; estiver definido, somente as primeiras N linhas serão fornecidas no relatório.
* **Layout 2**: o Data Warehouse aplica uma classificação de métrica em todas as linhas do relatório. Os vínculos no primeiro valor de métrica são quebrados pela segunda métrica e, em seguida, pela terceira e assim por diante. Quando todas as métricas são vinculadas, a ordem padrão do dicionário dos itens de linha de detalhamento é aplicada.
* **Layout 3**: como Layout 2, com apenas as N linhas principais (ou seja, o número definido em &quot;número máximo de linhas&quot;) sendo emitido no relatório.
* **Layout 4**: como Layout 2, com a exceção de que os itens de linha para cada período de granularidade de data são agrupados e classificados dentro desse intervalo de tempo respectivo.

Consulte a coluna &quot;Layout do relatório&quot; nesta tabela para determinar como &quot;Classificação de métricas&quot; interage com outras opções de relatórios do Data Warehouse.

| Classificar por métrica? | Tem métricas? | Têm Detalhamentos? | Granularidade de data? | Máximo de linhas definido? | Layout do relatório |
|---|---|---|---|---|---|
| Não | Sim ou Não | Sim ou Não | Sim ou Não | Sim ou Não | 1 |
| Sim | Não | Sim ou Não | Sim ou Não | Sim ou Não | 1 |
| Sim | Sim | Não | Não | N/D | 1 |
| Sim | Sim | Não | Sim ou Não | Não | 1 |
| Sim | Sim | Sim | Não | Não | 2 |
| Sim | Sim | Não | Sim | Sim | 3 |
| Sim | Sim | Sim | Sim ou Não | Sim | 3 |
| Sim | Sim | Sim | Sim | Não | 4 |
