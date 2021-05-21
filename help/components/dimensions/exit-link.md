---
title: Link de saída
description: O nome do link de saída.
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '156'
ht-degree: 100%

---

# Link de saída

A dimensão “Link de saída” informa os nomes dos links de saída implementados em seu site. Essa dimensão é valiosa quando você quer entender quais são os links mais populares que apontam para domínios fora do seu site.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da [`pev2`sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem para ocorrências que também têm a sequência de consulta `pe` com o valor de `lnk_e`. Se a sequência de consulta `pe` tiver um valor diferente na ocorrência, essa dimensão não coletará dados.

Se desejar enviar dados para essa dimensão usando o AppMeasurement, envie uma solicitação de imagem [`tl()`](/help/implement/vars/functions/tl-method.md) com um argumento de tipo de link de `"e"`. Preencha o argumento do nome do link com o valor desejado.

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios.
