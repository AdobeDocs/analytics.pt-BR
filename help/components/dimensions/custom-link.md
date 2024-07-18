---
title: Link personalizado
description: O nome do link personalizado.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 90%

---

# Link personalizado

A [dimensão](overview.md) de &#39;Link personalizado&#39; informa os nomes dos links personalizados implementados em seu site. Essa dimensão é importante quando você quer entender os tipos de links em que os visitantes mais clicam.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da [`pev2`sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem para ocorrências que também têm a sequência de consulta `pe` com o valor de `lnk_o`. Se a sequência de consulta `pe` tiver um valor diferente na ocorrência, essa dimensão não coletará dados.

Se desejar enviar dados para essa dimensão usando o AppMeasurement, envie uma solicitação de imagem [`tl()`](/help/implement/vars/functions/tl-method.md) com um argumento de tipo de link de `"o"`. Preencha o argumento do nome do link com o valor desejado.

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios.
