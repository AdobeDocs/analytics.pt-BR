---
title: Link de download
description: O nome do link de download.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: 418e8d467ca29267314e14fba99783d0cb3d05a9
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 28%

---

# Link de download

A [dimensão](overview.md) do &#39;Link de download&#39; relata os nomes dos links de download implementados em seu site. Essa dimensão é importante quando você deseja saber mais sobre o comportamento do visitante em links de download, como:

* Quais arquivos são baixados com mais frequência do site.
* Se determinados arquivos são baixados com mais frequência durante períodos específicos.
* Se os visitantes baixam tipos de arquivos diferentes quando oferecidos.

## Preencher esta dimensão com dados

Esta dimensão coleta dados da [`pev2` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem, dependendo do valor na sequência de consulta `pe`. A cadeia de consulta `pe` determina qual dimensão de link recebe o valor `pev2`:

* **[Link personalizado](custom-link.md)**: `lnk_o`
* **Link de download** (esta página): `lnk_d`
* **[Link de saída](exit-link.md)**: `lnk_e`

Se `pev2` não for fornecido, a URL do link (`pev1`) será usada como o valor da dimensão. Quando um nome de link é fornecido explicitamente, o comprimento máximo é de 100 bytes. Os valores derivados do URL do link não estão sujeitos a esse limite.

Para preencher esta dimensão usando o AppMeasurement, envie uma solicitação de imagem [`tl()`](/help/implement/vars/functions/tl-method.md) com um argumento de tipo de link de `"d"`. Defina o argumento do nome do link com o valor desejado:

```js
s.tl(true,"d","Example download link");
```

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios. Se nenhum nome de link for fornecido, os itens de dimensão aparecerão como URLs brutos. Esses URLs brutos são mais difíceis de interpretar nos relatórios, portanto, forneça um nome de link descritivo sempre que possível.
