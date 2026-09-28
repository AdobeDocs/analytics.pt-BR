---
title: Endereço IP
description: O endereço IP de onde cada ocorrência foi enviada, disponível no Data Warehouse.
feature: Dimensions
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
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 16%
---
# Endereço IP

A [dimensão](overview.md) do &#39;Endereço IP&#39; lista o endereço IP de onde cada ocorrência foi enviada.

>[!IMPORTANT]
>
>Essa dimensão só está disponível na Data Warehouse.

## Preencher esta dimensão com dados

O AppMeasurement coleta automaticamente o endereço IP do cabeçalho HTTP de cada solicitação de imagem. Corresponde à coluna `ip` nos feeds de dados. Consulte [Referência da coluna de dados](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) para obter mais informações.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (da solicitação HTTP) |
| **Web SDK / campo XDM** | Nenhum (da solicitação HTTP) |
| **Parâmetro de consulta** | Nenhum (da solicitação HTTP) |
| **Marca XML** | [`<ipAddress>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

Se a [!UICONTROL Ofuscação de IP] estiver habilitada nas [Configurações gerais de conta](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) do conjunto de relatórios, os endereços IP serão ofuscados ou removidos em todo o Analytics, incluindo o Data Warehouse.

## Itens de dimensão

Os itens do Dimension incluem os endereços IP dos quais as ocorrências foram enviadas.
