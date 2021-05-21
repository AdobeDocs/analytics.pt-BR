---
title: Perguntas frequentes sobre o Data Warehouse
description: Perguntas frequentes sobre Data Warehouse.
exl-id: 51c3ba17-a8b2-4030-9521-355ebbbfcd0d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '131'
ht-degree: 100%

---

# Perguntas frequentes sobre o Data Warehouse

Perguntas frequentes sobre Data Warehouse.

## Quando uso a lista suspensa de granularidade ao criar uma solicitação, em que formato posso esperar que as datas estejam?

Ao ser aplicada a granularidade em uma solicitação do Data Warehouse, a coluna &quot;Data&quot; é adicionada ao relatório. Dependendo da granularidade selecionada, o formato de data muda.

| Granularidade | Formato | Exemplo |
| --- | --- | --- |
| Por hora | `mmmm d, yyyy` Hora `H` | 1º de janeiro, 20XX, Hora 0 |
| Diariamente | `mmmm d, yyyy` | 1° de janeiro, 20XX |
| Semanalmente | Semana `w, yyyy` | Semana 1, 20XX |
| Mensalmente | `mmmm yyyy` | Janeiro de 20XX |
| Trimestralmente | `q` Trimestre `yyyy` | 1º trimestre de 20XX |
| Anualmente | `yyyy` | 20XX |

## Como os segmentos como dimensões funcionam no Data Warehouse?

Quando você usa um segmento como uma dimensão no Data Warehouse, o relatório retorna uma coluna que contém `"0"` ou `"1"`:

* **`"0"`**: o item de dimensão não atendeu aos critérios do segmento.
* **`"1"`**: o item de dimensão atendeu aos critérios do segmento.
