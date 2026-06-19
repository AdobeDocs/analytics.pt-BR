---
title: ID de visitante da Experience Cloud
description: A Experience Cloud ID (ECID) do visitante, disponível no Data Warehouse.
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 105
ht-degree: 21%

---

# ID de visitante da Experience Cloud

A [dimensão](overview.md) da &#39;ID de visitante da Experience Cloud&#39; fornece a Experience Cloud ID (ECID) para cada visitante. É um número de 128 bits que consiste em dois números concatenados de 64 bits preenchidos com 19 dígitos.

>[!IMPORTANT]
>
>Essa dimensão só está disponível na Data Warehouse.

## Preencher esta dimensão com dados

Essa dimensão requer uma implementação que use o Serviço da Experience Cloud ID (ECID). Corresponde à coluna `mcvisid` nos feeds de dados. Consulte [Referência da coluna de dados](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) para obter mais informações.

## Itens de dimensão

Os itens do Dimension incluem a Experience Cloud ID de cada visitante.
