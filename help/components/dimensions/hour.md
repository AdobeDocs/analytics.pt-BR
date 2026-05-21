---
title: Hora
description: A hora em que a métrica ocorreu.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
TQID: https://experienceleague.adobe.com/Gkigdxnrted-gkPoGCQMx229EvCmVvSt9Rr5QP-IfGU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 243
ht-degree: 94%

---

# Hora

A [dimensão](overview.md) de &quot;Hora&quot; informa a hora em que determinada métrica ocorreu (arredondada para baixo). O primeiro item de dimensão é a primeira hora no intervalo de datas, e o último item de dimensão é a última hora no intervalo de datas. Essa dimensão é importante para os relatórios de tendências, pois permite visualizar métricas ao longo do tempo.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

Os itens de dimensão incluem uma determinada hora dentro do intervalo de datas de um relatório ao lado de sua data. É formatado como `HH:HH YYYY-MM-DD`.

## Horário de verão

O horário de verão é uma prática em que os relógios são adiantados uma hora na primavera e atrasados uma hora no outono. Se o fuso horário de um conjunto de relatórios usar horário de verão, a Adobe ajusta os dados de acordo com essa hora.

* **Quando o horário de verão começar**: em março, os relatórios geralmente mostram um intervalo de uma hora nos dados em que o horário de verão começa. A hora não existia, portanto, não faz parte da coleção de dados. Observe que uma pequena quantidade de dados ainda pode chegar a essa hora. Os servidores de coleção de dados da Adobe levam vários segundos (até um minuto) para considerar os ajustes de horário de verão.
* **Quando o horário de verão terminar**: em novembro, os relatórios geralmente mostram uma hora dupla em que o horário de verão termina. A hora aconteceu duas vezes, então ambas as horas são agregadas nos relatórios.
