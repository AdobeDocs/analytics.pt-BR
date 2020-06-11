---
title: Link de saída
description: O nome do link de saída.
translation-type: tm+mt
source-git-commit: c9e696201d0e9ec97dcdd6ff797ca72244dcf366
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 2%

---


# Link de saída

A dimensão &#39;Link de saída&#39; relata os nomes dos links de saída implementados em seu site. Essa dimensão é valiosa quando você deseja entender quais links são mais populares que apontam para domínios fora do seu site.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da string [`pev2` de](/help/implement/validate/query-parameters.md) query em solicitações de imagem para ocorrências que também têm a string de `pe` query com o valor de `lnk_e`. Se a string do `pe` query tiver um valor diferente na ocorrência, essa dimensão não coletará dados.

Se desejar enviar dados para essa dimensão usando o AppMeasurement:

* Preencha a [`linkName`](/help/implement/vars/config-vars/linkname.md) variável com o valor desejado.
* Defina a variável [`linkType`](/help/implement/vars/config-vars/linktype.md) como `"e"`.
* Envie uma solicitação de [`tl()`](/help/implement/vars/functions/tl-method.md) imagem.

## Valores de dimensão

Como essa variável se baseia em uma sequência de caracteres personalizada na implementação, sua organização determina quais são os valores da dimensão. A Adobe recomenda que você agrupe links em categorias significativas com base nas suas necessidades de relatórios.
