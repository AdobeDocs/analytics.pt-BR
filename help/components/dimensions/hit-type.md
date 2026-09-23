---
title: Tipo de ocorrência
description: Determina se o hit foi em primeiro ou segundo plano.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
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
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
    internal-label: Mobile SDK
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 31%
---
# Tipo de hit

A [dimensão](overview.md) do &quot;Tipo de ocorrência&quot; determina se um aplicativo móvel estava em primeiro ou segundo plano quando a ocorrência foi enviada para os servidores de coleta de dados da Adobe. Essa dimensão só é relevante para conjuntos de relatórios que contêm dados para aplicativos móveis. Os dados do navegador coletados pelo AppMeasurement sempre relatam a ocorrência como `"Foreground"`.

## Preencher esta dimensão com dados

O Mobile SDK define a variável [`customerPerspective`](/help/implement/vars/page-vars/customerperspective.md) para indicar se cada ocorrência ocorreu em primeiro ou segundo plano. Essa dimensão funciona imediatamente em todas as implementações do SDK móvel na versão 4.13.6 ou superior. Se você não usar o SDK móvel, todas as ocorrências serão listadas em `"Foreground"`. Se **[!UICONTROL Impedir ocorrências em segundo plano de iniciar uma nova visita]** for selecionado ao configurar um [Conjunto de relatórios virtual](../vrs/vrs-mobile-visit-processing.md), as ocorrências em segundo plano não aumentarão as [[!UICONTROL Visitas]](../metrics/visits.md) e [[!UICONTROL Visitantes únicos]](../metrics/unique-visitors.md).

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | [`customerPerspective`](/help/implement/vars/page-vars/customerperspective.md) |
| **Web SDK / campo XDM** | Nenhum |
| **Parâmetro de consulta** | [`cp`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<customerPerspective>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem `"Foreground"` e `"Background"`. As ocorrências em segundo plano só ocorrem em dispositivos móveis nos quais o aplicativo rastreado está em segundo plano.
