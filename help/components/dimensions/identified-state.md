---
title: Estado identificado
description: Um sinalizador que determina o reconhecimento para compilação.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
TQID: https://experienceleague.adobe.com/JUBtgXBDboIgX0xbvuflF5q-oEwqHx4vKvJd0Y5XMLY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
source-wordcount: '175'
ht-degree: 46%
---
# Estado identificado

A [dimensão](overview.md) de &#39;Estado identificado&#39; é específica para os conjuntos de relatórios virtuais do [Cross-Device Analytics](../cda/overview.md). Ele relata se os hits são identificados (compiladas) ou não pelo sistema no momento em que o relatório é executado. Essa dimensão é útil para entender o quão bem o CDA costuma compilar ou &quot;compactar&quot; dados.

## Preencher esta dimensão com dados

Esta dimensão é calculada pela [Análise entre dispositivos](../cda/overview.md) no momento em que um relatório é executado, com base no fato de cada ocorrência ter sido compilada a uma pessoa. Desde que o Cross-Device Analytics esteja configurado para um conjunto de relatórios virtual, ele funcionará imediatamente; não há variável a ser definida.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (calculado pela Análise entre dispositivos) |
| **Web SDK / campo XDM** | Nenhum (calculado pela Análise entre dispositivos) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: o hit é mapeado para uma pessoa.
* **`"Unidentified"`**: o hit não é mapeado para uma pessoa e não pode ser mapeado por nenhum método de atribuição.
