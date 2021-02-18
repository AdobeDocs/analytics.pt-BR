---
title: Link personalizado
description: O nome do link personalizado.
translation-type: ht
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: ht
source-wordcount: '152'
ht-degree: 100%

---


# Link personalizado

A dimensão “Link personalizado” informa os nomes dos links personalizados implementados em seu site. Essa dimensão é importante quando você quer entender os tipos de links em que os visitantes mais clicam.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da [`pev2`sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem para ocorrências que também têm a sequência de consulta `pe` com o valor de `lnk_o`. Se a sequência de consulta `pe` tiver um valor diferente na ocorrência, essa dimensão não coletará dados.

Se desejar enviar dados para essa dimensão usando o AppMeasurement, envie uma solicitação de imagem [`tl()`](/help/implement/vars/functions/tl-method.md) com um argumento de tipo de link de `"o"`. Preencha o argumento do nome do link com o valor desejado.

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios.
