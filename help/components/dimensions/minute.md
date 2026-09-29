---
title: Minuto
description: O minuto em que a métrica ocorreu.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
TQID: 'https://experienceleague.adobe.com/GRivRprXBteGxRZieSI3uyjHALDJ-0hHbZx3S9ldJW0'
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 55%
---
# Minuto

O &#39;Minuto&#39; [dimensão](overview.md) informa o minuto em que uma determinada métrica ocorreu (arredondado para baixo). O primeiro item de dimensão é o primeiro minuto no intervalo de datas, e o último item de dimensão é o último minuto no intervalo de datas. Essa dimensão é importante para os relatórios de tendências, pois permite visualizar métricas ao longo do tempo. Dada a grandeza dessa dimensão, a Adobe recomenda limitar o intervalo de datas dos relatórios a um ou dois dias.

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

Os itens de dimensão incluem um determinado minuto dentro do intervalo de datas de um relatório ao lado de sua data. É formatado como `HH:MM YYYY-MM-DD`. Itens de Dimension que começam com `00:00` são iguais a meia-noite nesse dia, enquanto valores que começam com `23:59` são iguais a 23h59 para aquele dia.
