---
title: Link personalizado
description: O nome do link personalizado.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 2%

---


# Link personalizado

A dimensão &#39;Link personalizado&#39; relata os nomes dos links personalizados implementados em seu site. Essa dimensão é importante quando você deseja entender os tipos de links em que os visitantes mais clicam.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da string [`pev2` de](/help/implement/validate/query-parameters.md) query em solicitações de imagem para ocorrências que também têm a string de `pe` query com o valor de `lnk_o`. Se a string do `pe` query tiver um valor diferente na ocorrência, essa dimensão não coletará dados.

Se desejar enviar dados para essa dimensão usando o AppMeasurement:

* Preencha a [`linkName`](/help/implement/vars/config-vars/linkname.md) variável com o valor desejado.
* Defina a variável [`linkType`](/help/implement/vars/config-vars/linktype.md) como `"o"`.
* Envie uma solicitação de [`tl()`](/help/implement/vars/functions/tl-method.md) imagem.

## Itens de dimensão

Como essa variável se baseia em uma sequência de caracteres personalizada na implementação, sua organização determina quais itens de dimensão são. A Adobe recomenda que você agrupe links em categorias significativas com base nas suas necessidades de relatórios.
