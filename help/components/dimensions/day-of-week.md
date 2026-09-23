---
title: Dia da semana
description: O dia da semana, independentemente do intervalo de datas.
feature: Dimensions
exl-id: 01aa6b5f-49e6-4f86-97c7-8d0ff431e15b
TQID: https://experienceleague.adobe.com/9nudTrYTDMEFXSo81uUuw9KFT3mRPhZer3cX81AwoPM
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
source-wordcount: '167'
ht-degree: 62%
---
# Dia da semana

A [dimensão](overview.md) de &quot;Dia da semana&quot; informa o dia da semana em que a ocorrência aconteceu. Este relatório é importante se você quiser que um relatório seja dividido por semana, mas não quiser dias estáticos como itens de dimensão. Ela é especialmente valiosa como uma dimensão em relatórios programados, já que essa dimensão funciona com qualquer intervalo de datas.

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

Os itens de dimensão incluem `Sunday` - `Saturday`, representando o dia da semana em que o hit aconteceu. A ordem dos itens de dimensão respeita o primeiro dia da semana em [Personalizar calendário](/help/admin/tools/manage-rs/edit-settings/general/custom-calendar.md) por padrão.
