---
title: Hora
description: A hora em que a métrica ocorreu.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
TQID: 'https://experienceleague.adobe.com/Gkigdxnrted-gkPoGCQMx229EvCmVvSt9Rr5QP-IfGU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 78%
---
# Hora

A [dimensão](overview.md) de &quot;Hora&quot; informa a hora em que determinada métrica ocorreu (arredondada para baixo). O primeiro item de dimensão é a primeira hora no intervalo de datas, e o último item de dimensão é a última hora no intervalo de datas. Essa dimensão é importante para os relatórios de tendências, pois permite visualizar métricas ao longo do tempo.

## Preencher esta dimensão com dados

Essa dimensão é derivada do carimbo de data e hora de cada ocorrência. Não há variável a ser definida; isso funciona imediatamente em qualquer implementação.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado do carimbo de data e hora da ocorrência) |
| **Web SDK / campo XDM** | Nenhum (derivado do carimbo de data e hora da ocorrência) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | Hit |

## Itens de dimensão

Os itens de dimensão incluem uma determinada hora dentro do intervalo de datas de um relatório ao lado de sua data. É formatado como `HH:HH YYYY-MM-DD`.

## Horário de verão

O horário de verão é uma prática em que os relógios são adiantados uma hora na primavera e atrasados uma hora no outono. Se o fuso horário de um conjunto de relatórios usar horário de verão, a Adobe ajusta os dados de acordo com essa hora.

* **Quando o horário de verão começar**: em março, os relatórios geralmente mostram um intervalo de uma hora nos dados em que o horário de verão começa. A hora não existia, portanto, não faz parte da coleção de dados. Observe que uma pequena quantidade de dados ainda pode chegar a essa hora. Os servidores de coleção de dados da Adobe levam vários segundos (até um minuto) para considerar os ajustes de horário de verão.
* **Quando o horário de verão terminar**: em novembro, os relatórios geralmente mostram uma hora dupla em que o horário de verão termina. A hora aconteceu duas vezes, então ambas as horas são agregadas nos relatórios.
