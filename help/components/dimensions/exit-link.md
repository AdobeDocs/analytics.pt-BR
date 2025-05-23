---
title: Link de saída
description: O nome do link de saída.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 75%

---

# Link de saída

O &#39;Link de saída&#39; [dimensão](overview.md) informa os nomes dos links de saída implementados em seu site. Essa dimensão é valiosa quando você quer entender quais são os links mais populares que apontam para domínios fora do seu site.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da [`pev2`sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem para ocorrências que também têm a sequência de consulta `pe` com o valor de `lnk_e`. Se a sequência de consulta `pe` tiver um valor diferente na ocorrência, essa dimensão não coletará dados. O comprimento máximo dessa dimensão é de 100 bytes.

Se desejar enviar dados para essa dimensão usando o AppMeasurement, envie uma solicitação de imagem [`tl()`](/help/implement/vars/functions/tl-method.md) com um argumento de tipo de link de `"e"`. Preencha o argumento do nome do link com o valor desejado.

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios.
