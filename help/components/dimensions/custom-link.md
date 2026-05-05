---
title: Link personalizado
description: O nome do link personalizado.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: 5c1d50fa09b0fad228f24018de2b062d09b0fe5f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 21%

---

# Link personalizado

A [dimensão](overview.md) de &#39;Link personalizado&#39; informa os nomes dos links personalizados implementados em seu site. Os links personalizados são um mecanismo de rastreamento flexível para qualquer interação que não seja um download de arquivo ou uma navegação de saída. Exemplos comuns incluem cliques de botão, navegação interna ou interações de formulário. Essa dimensão é importante quando você quer entender com quais dessas interações os visitantes interagem mais.

## Preencher esta dimensão com dados

Esta dimensão coleta dados da [`pev2` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem, dependendo do valor na sequência de consulta `pe`. A cadeia de consulta `pe` determina qual dimensão de link recebe o valor `pev2`:

* **Link personalizado** (esta página): `lnk_o`
* **[Link de download](download-link.md)**: `lnk_d`
* **[Link de saída](exit-link.md)**: `lnk_e`

Se `pev2` não for fornecido, a URL do link (`pev1`) será usada como o valor da dimensão. Quando um nome de link é fornecido explicitamente, o comprimento máximo é de 100 bytes. Os valores derivados do URL do link não estão sujeitos a esse limite.

Para preencher esta dimensão usando o AppMeasurement, envie uma solicitação de imagem [`tl()`](/help/implement/vars/functions/tl-method.md) com um argumento de tipo de link de `"o"`. Defina o argumento do nome do link com o valor desejado:

```js
s.tl(true,"o","Example custom link");
```

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios. Se nenhum nome de link for fornecido, os itens de dimensão aparecerão como URLs brutos. Esses URLs brutos são mais difíceis de interpretar nos relatórios, portanto, forneça um nome de link descritivo sempre que possível.
