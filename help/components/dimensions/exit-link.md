---
title: Link de saída
description: O nome do link de saída.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
TQID: https://experienceleague.adobe.com/lGKBkR5e2arJxGmfIE4qN84oGtYJ2zkfn6luqxEUJ-w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 22%

---

# Link de saída

O &#39;Link de saída&#39; [dimensão](overview.md) informa os nomes dos links de saída implementados em seu site. Os links de saída rastreiam os cliques de saída que afastam os visitantes do domínio atual. Essa dimensão é importante quando você quer entender quais links externos são clicados com mais frequência.

## Preencher esta dimensão com dados

Esta dimensão coleta dados da [`pev2` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem, dependendo do valor na sequência de consulta `pe`. A cadeia de consulta `pe` determina qual dimensão de link recebe o valor `pev2`:

* **[Link personalizado](custom-link.md)**: `lnk_o`
* **[Link de download](download-link.md)**: `lnk_d`
* **Link de saída** (esta página): `lnk_e`

Se `pev2` não for fornecido, a URL do link (`pev1`) será usada como o valor da dimensão. Quando um nome de link é fornecido explicitamente, o comprimento máximo é de 100 bytes. Os valores derivados do URL do link não estão sujeitos a esse limite.

Para preencher esta dimensão usando o AppMeasurement, envie uma solicitação de imagem [`tl()`](/help/implement/vars/functions/tl-method.md) com um argumento de tipo de link de `"e"`. Defina o argumento do nome do link com o valor desejado:

```js
s.tl(true,"e","Example exit link");
```

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios. Se nenhum nome de link for fornecido, os itens de dimensão aparecerão como URLs brutos. Esses URLs brutos são mais difíceis de interpretar nos relatórios, portanto, forneça um nome de link descritivo sempre que possível.
