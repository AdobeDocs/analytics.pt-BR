---
title: Pesquisa paga
description: Distingue métricas de pesquisa paga e natural.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
TQID: https://experienceleague.adobe.com/s9jhjGeXaOCo-Wz-Jyof951NZdRWfz-9tjrVrjHvTS0
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 59%
---
# Pesquisa paga

A [dimensão](overview.md) de &quot;Pesquisa paga&quot; permite que você veja qualquer métrica e a compare entre a pesquisa paga e a pesquisa natural. Todos os outros hits fora dos mecanismos de pesquisa são omitidos. Essa dimensão é útil para entender como seus esforços de pesquisa paga se comparam com a pesquisa orgânica.

## Preencher esta dimensão com dados

A Adobe deriva essa dimensão pela detecção de pesquisa paga, que classifica o tráfego do mecanismo de pesquisa como pago ou natural. Não há variável a ser definida. O único requisito é ter a [Detecção de pesquisa paga](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) definida corretamente nas configurações do conjunto de relatórios. Se a detecção de pesquisa paga estiver configurada corretamente e um conjunto de relatórios tiver dados, essa dimensão sempre funcionará.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado de detecção de pesquisa paga) |
| **Web SDK / campo XDM** | Nenhum (derivado de detecção de pesquisa paga) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão têm dois valores estáticos: `"Natural"` e `"Paid"`. Se uma visita corresponder aos critérios de um mecanismo de pesquisa e também corresponder à detecção de pesquisa paga, ela pertencerá ao item de dimensão `"Paid"`. Se uma visita corresponder aos critérios de um mecanismo de pesquisa e *não* corresponder à detecção de pesquisa paga, ela pertencerá ao item de dimensão `"Natural"`.
