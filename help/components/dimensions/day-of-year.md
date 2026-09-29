---
title: Dia do ano
description: O dia numérico do ano, independentemente do ano.
feature: Dimensions
exl-id: 40a95926-3d1b-4e9c-a82a-6e23b711e6e7
TQID: 'https://experienceleague.adobe.com/X-Is9URgykjJAAdTlJjzqQnrHMlAnzyoC2tMFT2q9T0'
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
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 56%
---
# Dia do ano

A [dimensão](overview.md) de &quot;Dia do ano&quot; informa o dia numérico de um determinado ano como um item de dimensão. Esse relatório é importante se você quiser que um relatório seja dividido pelo dia do ano, mas não quiser uma data estática como itens de dimensão.

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

Os itens de dimensão incluem os números `1` (1° de janeiro) a `366` (31 de dezembro no ano bissexto), representando o dia do ano em que o hit aconteceu.
