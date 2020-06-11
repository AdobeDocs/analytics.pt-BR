---
title: Link de download
description: O nome do link de download.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 17%

---


# Link de download

A dimensão &#39;Baixar link&#39; relata os nomes dos links de download implementados em seu site. Essa dimensão é importante quando você deseja saber mais sobre o comportamento do visitante em links de download, como:

* Determine os arquivos que são transferidos por download com mais frequência do site.
* Entenda se certos arquivos que são transferidos por download com mais frequência durante períodos de tempo específicos.
* Valide se os visitantes baixam tipos de arquivo diferentes se houver.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da string [`pev2` de](/help/implement/validate/query-parameters.md) query em solicitações de imagem para ocorrências que também têm a string de `pe` query com o valor de `lnk_d`. Se a string do `pe` query tiver um valor diferente na ocorrência, essa dimensão não coletará dados.

Se desejar enviar dados para essa dimensão usando o AppMeasurement:

* Preencha a [`linkName`](/help/implement/vars/config-vars/linkname.md) variável com o valor desejado.
* Defina a variável [`linkType`](/help/implement/vars/config-vars/linktype.md) como `"d"`.
* Envie uma solicitação de [`tl()`](/help/implement/vars/functions/tl-method.md) imagem.

## Valores de dimensão

Como essa variável se baseia em uma sequência de caracteres personalizada na implementação, sua organização determina quais são os valores da dimensão. A Adobe recomenda que você agrupe links em categorias significativas com base nas suas necessidades de relatórios.
