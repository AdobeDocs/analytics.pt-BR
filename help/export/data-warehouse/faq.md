---
title: Perguntas frequentes sobre Data Warehouse
description: Perguntas frequentes sobre Data Warehouse.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 9%

---


# Perguntas frequentes sobre Data Warehouse

Perguntas frequentes sobre Data Warehouse.

## Quando eu uso a lista suspensa de granularidade ao criar uma solicitação, em que formato posso esperar que as datas estejam?

Ao aplicar a granularidade em uma solicitação de Data Warehouse, a coluna &quot;Data&quot; é adicionada ao relatório. Dependendo da granularidade selecionada, o formato de data muda.

| Granularidade | Formato | Exemplo |
| --- | --- | --- |
| Por hora | `mmmm d, yyyy` Hora `H` | 1º de janeiro de 20XX, Hora 0 |
| Diariamente | `mmmm d, yyyy` | 1 de janeiro de 2000 XX |
| Semanalmente | Semana `w, yyyy` | Semana 1, 20XX |
| Mensalmente | `mmmm yyyy` | 20XX de janeiro |
| Trimestralmente | `q` Trimestre `yyyy` | Primeiro trimestre 20XX |
| Anualmente | `yyyy` | 20XX |

## Como os segmentos como dimensões funcionam na Data Warehouse?

Quando você usa um segmento como uma dimensão na Data Warehouse, o relatório retorna uma coluna contendo `"0"` ou `"1"`:

* **`"0"`**: O item de dimensão não atendia aos critérios do segmento.
* **`"1"`**: O item de dimensão atendeu aos critérios do segmento.
