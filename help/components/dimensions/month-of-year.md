---
title: Mês do ano
description: O mês numérico, independentemente do ano.
feature: Dimensions
exl-id: ed2887f2-46e7-48a4-b337-f59177c7558c
TQID: https://experienceleague.adobe.com/W62Cro1mGRZnEY-v1ilx9Dw1Xu0qR4t-KSVkOpG8RGY
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
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 61%
---
# Mês do ano

A [dimensão](overview.md) de &quot;Mês do ano&quot; informa o mês de um determinado ano como um item de dimensão. Esse relatório é importante se você quiser que um relatório seja dividido pelo mês do ano, mas não quiser uma data estática como itens de dimensão. Você pode agregar relatórios anuais por mês, de forma que os dados de janeiro deste ano sejam agregados aos dados de janeiro do ano passado no mesmo item de dimensão.

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

Os itens de dimensão incluem os meses do ano (`January` a `December`), representando o mês do ano em que o hit aconteceu.
