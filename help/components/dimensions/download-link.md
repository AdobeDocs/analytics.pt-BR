---
title: Link de download
description: O nome do link de download.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 87%

---


# Link de download

A dimensão “Link de download” relata os nomes dos links de download implementados em seu site. Essa dimensão é importante quando você deseja saber mais sobre o comportamento do visitante em links de download, como:

* Determine os arquivos que são transferidos por download com mais frequência do site.
* Entenda se certos arquivos que são transferidos por download com mais frequência durante períodos de tempo específicos.
* Confirmar se os visitantes baixam tipos de arquivo diferentes, se estiverem disponíveis.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da [`pev2`sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem para ocorrências que também têm a sequência de consulta `pe` com o valor de `lnk_d`. Se a sequência de consulta `pe` tiver um valor diferente na ocorrência, essa dimensão não coletará dados.

Se desejar enviar dados para essa dimensão usando o AppMeasurement:

* Preencha a variável [`linkName`](/help/implement/vars/config-vars/linkname.md) com o valor desejado.
* Defina a variável [`linkType`](/help/implement/vars/config-vars/linktype.md) como `"d"`.
* Envie uma solicitação de imagem [`tl()`](/help/implement/vars/functions/tl-method.md).

## itens de Dimension

Como essa variável se baseia em uma sequência de caracteres personalizada na implementação, sua organização determina quais itens de dimensão são. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios.
