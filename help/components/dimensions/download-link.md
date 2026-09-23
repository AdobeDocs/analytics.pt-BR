---
title: Link de download
description: O nome do link de download.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
TQID: https://experienceleague.adobe.com/vok8Znalf6GBA1N0Z9GE1d31QpaUmD-d0bOsHB2Wehc
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
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 27%
---
# Link de download

A [dimensão](overview.md) do &#39;Link de download&#39; relata os nomes dos links de download implementados em seu site. Essa dimensão é importante quando você deseja saber mais sobre o comportamento do visitante em links de download, como:

* Quais arquivos são baixados com mais frequência do site.
* Se determinados arquivos são baixados com mais frequência durante períodos específicos.
* Se os visitantes baixam tipos de arquivos diferentes quando oferecidos.

## Preencher esta dimensão com dados

Esta dimensão foi preenchida por [chamadas de rastreamento de link (`tl()`)](/help/implement/vars/functions/tl-method.md). Não há variável dedicada para definir. Em vez disso, envie uma solicitação de imagem `tl()` com um argumento de tipo de link de `"d"` e defina o argumento de nome do link com o valor desejado. A cadeia de consulta `pe` roteia o nome do link para a dimensão de link correta (`lnk_o` para [links personalizados](custom-link.md), `lnk_d` para [links de download](download-link.md) e `lnk_e` para [links de saída](exit-link.md)). Se um nome de link não for fornecido, o URL do link será usado como o valor da dimensão, e os valores derivados do URL não estarão sujeitos ao limite de bytes.

```js
s.tl(true,"d","Example download link");
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
