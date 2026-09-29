---
title: Seção do site
description: O nome da seção do site.
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
TQID: 'https://experienceleague.adobe.com/fZwN-24--98XULDEgHR-5dcIsiYXspaSOsv1t-M0iys'
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
source-wordcount: '179'
ht-degree: 66%
---
# Seção do site

A [dimensão](overview.md) de &#39;Seção do site&#39; lista os nomes das seções do site. Para sites grandes, é útil agrupar páginas em seções. Essa dimensão é útil para ver as seções de site com melhor desempenho ou as mais exibidas.

Essa dimensão está relacionada às dimensões [Página](page.md) e [Servidor](server.md). A dimensão Página é mais granular, a dimensão Servidor é menos granular e a dimensão Seção do site fica entre as duas.

## Preencher esta dimensão com dados

O AppMeasurement coleta esses dados usando a variável [`channel`](/help/implement/vars/page-vars/channel.md).

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | [`channel`](/help/implement/vars/page-vars/channel.md) |
| **Web SDK / campo XDM** | [`web.webPageDetails.siteSection`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parâmetro de consulta** | [`ch`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<channel>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | 100 bytes |
| **Persistência** | Hit |

## Itens de dimensão

Os itens de dimensão incluem os nomes das seções do site. A organização escolhe quais itens de dimensão específicos quer utilizar. Independentemente do método usado, verifique se ele é consistente e registre-o em um [documento de design de solução](/help/implement/prepare/solution-design.md).
