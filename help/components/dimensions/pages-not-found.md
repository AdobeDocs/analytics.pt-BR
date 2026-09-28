---
title: Páginas não encontradas (dimensões)
description: URLs que retornaram um erro ao site.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: 'https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc'
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
source-wordcount: '276'
ht-degree: 48%
---
# Páginas não encontradas

>[!BEGINSHADEBOX]

*Esta página de ajuda descreve como a dimensão &quot;Páginas não encontradas&quot; funciona como uma [dimensão](overview.md). Consulte a página de métricas [Páginas não encontradas](../metrics/pages-not-found.md) para obter informações sobre como ela funciona como uma métrica.*

>[!ENDSHADEBOX]

A dimensão “Páginas não encontradas” exibe URLs que continham um erro. Essa dimensão é útil quando você deseja diminuir o número de erros que os visitantes recebem no site.

* É possível utilizar essa dimensão em uma [Visualização de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para ver em quais páginas os visitantes clicam para chegar ao erro. Em seguida, você pode trabalhar com equipes de desenvolvimento em sua organização para corrigir o link em cada página.
* É possível utilizar essa dimensão com a dimensão [“Referenciador”](referrer.md) para ver o lugar no site que os visitantes chegam quando eles vêm de links externos. É possível implementar redirecionamentos para o local desejado ou trabalhar com terceiros para corrigir o link.

>[!NOTE]
>
>No Data Warehouse, essa dimensão se chama &#39;[!UICONTROL Erro de Tipo de Página]&#39;.

## Preencher esta dimensão com dados

O AppMeasurement coleta esses dados usando a variável [`pageType`](/help/implement/vars/page-vars/pagetype.md). Quando `pageType` está definido como `errorPage`, a URL da página da ocorrência é registrada como um item de dimensão. Se a variável `pageType` não estiver definida ou estiver definida com qualquer outro valor, nenhum dado para essa dimensão será coletado.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | [`pageType`](/help/implement/vars/page-vars/pagetype.md) |
| **Web SDK / campo XDM** | [`web.webPageDetails.isErrorPage`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parâmetro de consulta** | [`pageType`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<pageType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | N/D |
| **Persistência** | Hit |

## Itens de dimensão

Os itens de dimensão incluem os URLs das páginas do site em que ocorreu um erro.
