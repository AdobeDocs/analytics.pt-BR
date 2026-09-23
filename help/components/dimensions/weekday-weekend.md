---
title: Dia da semana/Fim de semana
description: Determina se o hit ocorreu durante um dia da semana ou um fim de semana.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
TQID: https://experienceleague.adobe.com/9TJv-49ub1zHsgEGtBeoJVoHhsBktlOr7QhmgLdLRSo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
source-wordcount: '155'
ht-degree: 49%
---
# Dia da semana/Fim de semana

A [dimensão](overview.md) de &quot;Dia da semana/Fim de semana&quot; fornece o insight sobre se a ocorrência aconteceu durante um dia da semana (de segunda a sexta-feira) ou no fim de semana (sábado a domingo). O horário do hit tem como base o [fuso horário do conjunto de relatórios](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão é derivada do carimbo de data e hora de cada ocorrência; não há variável para definir. Sua única dependência é o fuso horário do conjunto de relatórios, que determina o dia da semana para cada ocorrência.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado do carimbo de data e hora da ocorrência) |
| **Web SDK / campo XDM** | Nenhum (derivado do carimbo de data e hora da ocorrência) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | Hit |

## Itens de dimensão

Essa dimensão sempre contém exatamente dois itens de dimensão: `"Weekday"` e `"Weekend"`. O item de dimensão `"Weekday"` se aplica a todos os hits de segunda a sexta-feira, enquanto o item de dimensão `"Weekend"` se aplica a todos os hits de sábado e domingo.
