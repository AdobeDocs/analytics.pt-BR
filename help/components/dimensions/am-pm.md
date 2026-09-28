---
title: AM/PM
description: Determina se o hit aconteceu durante as horas AM ou PM.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: 'https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 33%
---
# AM/PM

A [dimensão](overview.md) de &quot;AM/PM&quot; fornece o insight sobre se a ocorrência aconteceu durante as horas AM ou PM. O horário do hit tem como base o [fuso horário do conjunto de relatórios](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Preencher esta dimensão com dados

Essa dimensão é derivada do carimbo de data e hora de cada ocorrência; não há variável para definir. Sua única dependência é o fuso horário do conjunto de relatórios, que determina quais horas são AM e quais são PM.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado do carimbo de data e hora da ocorrência) |
| **Web SDK / campo XDM** | Nenhum (derivado do carimbo de data e hora da ocorrência) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | Hit |

## Itens de dimensão

Essa dimensão sempre contém exatamente dois itens de dimensão: `"AM"` e `"PM"`. O item de dimensão `"AM"` se aplica a todas as ocorrências de 12:00 AM às 11:59 AM, enquanto o item de dimensão `"PM"` se aplica a todas as ocorrências de 12:00 PM às 11:59 PM.
