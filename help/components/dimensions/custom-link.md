---
title: Link personalizado
description: O nome do link personalizado.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
TQID: 'https://experienceleague.adobe.com/x4IAGJjozPnLsft1e9xs68L6TNDJbHW0H4Z23p9EDNg'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 20%
---
# Link personalizado

A [dimensão](overview.md) de &#39;Link personalizado&#39; informa os nomes dos links personalizados implementados em seu site. Os links personalizados são um mecanismo de rastreamento flexível para qualquer interação que não seja um download de arquivo ou uma navegação de saída. Exemplos comuns incluem cliques de botão, navegação interna ou interações de formulário. Essa dimensão é importante quando você quer entender com quais dessas interações os visitantes interagem mais.

## Preencher esta dimensão com dados

Esta dimensão foi preenchida por [chamadas de rastreamento de link (`tl()`)](/help/implement/vars/functions/tl-method.md). Não há variável dedicada para definir. Em vez disso, envie uma solicitação de imagem `tl()` com um argumento de tipo de link de `"o"` e defina o argumento de nome do link com o valor desejado. A cadeia de consulta `pe` roteia o nome do link para a dimensão de link correta (`lnk_o` para [links personalizados](custom-link.md), `lnk_d` para [links de download](download-link.md) e `lnk_e` para [links de saída](exit-link.md)). Se um nome de link não for fornecido, o URL do link será usado como o valor da dimensão, e os valores derivados do URL não estarão sujeitos ao limite de bytes.

```js
s.tl(true,"o","Example custom link");
```

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | [`tl()`](/help/implement/vars/functions/tl-method.md) |
| **Web SDK / campo XDM** | Nenhum |
| **Parâmetro de consulta** | [`pev2`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<linkName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | 100 bytes |
| **Persistência** | Hit |

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios. Se nenhum nome de link for fornecido, os itens de dimensão aparecerão como URLs brutos. Esses URLs brutos são mais difíceis de interpretar nos relatórios, portanto, forneça um nome de link descritivo sempre que possível.
