---
title: Página
description: O nome da página.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: 'https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
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
source-wordcount: '226'
ht-degree: 54%
---
# Página

A [dimensão](overview.md) de &quot;Página&quot; lista os nomes das páginas do site. É uma das dimensões mais comuns usadas no Adobe Analytics, pois fornece informações sobre quais páginas do site têm melhor desempenho.

Essa dimensão está relacionada à [Seção do site](site-section.md) e às dimensões de [Servidor](server.md). A dimensão Página é mais granular, a dimensão Servidor é menos granular e a dimensão Seção do site fica entre as duas.

## Preencher esta dimensão com dados

Defina a variável [`pageName`](/help/implement/vars/page-vars/pagename.md) em [Chamadas de exibição de página (`t()`)](/help/implement/vars/functions/t-method.md). Se a variável `pageName` não estiver definida, essa dimensão voltará a usar a variável [`pageURL`](/help/implement/vars/page-vars/pageurl.md). [As chamadas de rastreamento de link (`tl()`)](/help/implement/vars/functions/tl-method.md) sempre removem essa dimensão, mesmo se o valor `pageName` existir.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | [`pageName`](/help/implement/vars/page-vars/pagename.md) |
| **Web SDK / campo XDM** | [`web.webPageDetails.name`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parâmetro de consulta** | [`pageName`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<pageName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | 100 bytes |
| **Persistência** | Hit |

## Itens de dimensão

Os itens de dimensão incluem os nome de páginas no site. Sua organização determina quais itens de dimensão específicos deseja usar. Algumas organizações usam diretamente `document.title`, enquanto outras formulam uma navegação estrutural personalizada. Independentemente do método usado, verifique se ele é consistente e registre-o em um [documento de design de solução](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>O Analysis Workspace usa a última atribuição por padrão, com a opção de usar qualquer modelo de atribuição.
