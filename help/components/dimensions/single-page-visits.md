---
title: Visitas em única página (dimensões)
description: Um sinalizador que indica que a visita consistiu de uma única página.
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
TQID: 'https://experienceleague.adobe.com/mMxxlVpQi7IsSuxSZGijnvWeoqCa-ybf8otPRDf6AyQ'
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
source-wordcount: '187'
ht-degree: 64%
---
# Visitas em única página

>[!BEGINSHADEBOX]

*Esta página de ajuda descreve como &#39;Visitas em única página&#39; funciona como uma [dimensão](overview.md). Consulte a métrica [Visitas em única página](../metrics/single-page-visits.md) para obter mais informações.*

>[!ENDSHADEBOX]

A dimensão “Visitas em única página” informa o número de visitas que consistiam de um único item de dimensão [Página](page.md). É o formato da dimensão da métrica [Visitas em única página](../metrics/single-page-visits.md).

Essa dimensão é utilizada mais frequentemente como um componente dentro da [segmentação](../segmentation/seg-home.md). Ela geralmente não é utilizada como uma dimensão em relatórios.

## Preencher esta dimensão com dados

O Adobe calcula essa dimensão no lado do servidor avaliando se cada visita continha uma única página exclusiva. Não há variável a ser definida; isso funciona imediatamente em todas as implementações.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (calculado pela Adobe) |
| **Web SDK / campo XDM** | Nenhum (calculado pela Adobe) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

O único item de dimensão é `"Enabled"`. Se uma visita consistir numa única página, o hit é definido como esse valor. Todos os outros hits são omitidos deste relatório.
