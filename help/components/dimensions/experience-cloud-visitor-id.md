---
title: ID de visitante da Experience Cloud
description: A Experience Cloud ID (ECID) do visitante, disponível no Data Warehouse.
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 18%
---
# ID de visitante da Experience Cloud

A [dimensão](overview.md) da &#39;ID de visitante da Experience Cloud&#39; fornece a ECID para cada visitante. É um número de 128 bits que consiste em dois números concatenados de 64 bits preenchidos com 19 dígitos.

>[!IMPORTANT]
>
>Essa dimensão só está disponível na Data Warehouse.

## Preencher esta dimensão com dados

Essa dimensão requer uma implementação que use o Serviço de ID de visitante (VisitorAPI) ou o Serviço de identidade da Experience Platform. Corresponde à coluna `mcvisid` nos feeds de dados. Consulte [Referência da coluna de dados](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) para obter mais informações.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (definido pelo Serviço de ID de visitante da Experience Cloud) |
| **Web SDK / campo XDM** | Nenhum (definido pelo serviço de identidade da Experience Cloud) |
| **Parâmetro de consulta** | [`mid`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<marketingCloudVisitorId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Os itens do Dimension incluem a Experience Cloud ID de cada visitante.
