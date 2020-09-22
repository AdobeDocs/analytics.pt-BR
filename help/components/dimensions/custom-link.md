---
title: Link personalizado
description: O nome do link personalizado.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '148'
ht-degree: 100%

---


# Link personalizado

A dimensão “Link personalizado” informa os nomes dos links personalizados implementados em seu site. Essa dimensão é importante quando você quer entender os tipos de links em que os visitantes mais clicam.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da [`pev2`sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem para ocorrências que também têm a sequência de consulta `pe` com o valor de `lnk_o`. Se a sequência de consulta `pe` tiver um valor diferente na ocorrência, essa dimensão não coletará dados.

Se desejar enviar dados para essa dimensão usando o AppMeasurement:

* Preencha a variável [`linkName`](/help/implement/vars/config-vars/linkname.md) com o valor desejado.
* Defina a variável [`linkType`](/help/implement/vars/config-vars/linktype.md) como `"o"`.
* Envie uma solicitação de imagem [`tl()`](/help/implement/vars/functions/tl-method.md).

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios.
