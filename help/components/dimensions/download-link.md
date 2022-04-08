---
title: Link de download
description: O nome do link de download.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '184'
ht-degree: 100%

---

# Link de download

A dimensão “Link de download” relata os nomes dos links de download implementados em seu site. Essa dimensão é importante quando você deseja saber mais sobre o comportamento do visitante em links de download, como:

* Determine os arquivos que são transferidos por download com mais frequência do site.
* Entenda se certos arquivos que são transferidos por download com mais frequência durante períodos de tempo específicos.
* Confirmar se os visitantes baixam tipos de arquivo diferentes, se estiverem disponíveis.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da [`pev2`sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem para ocorrências que também têm a sequência de consulta `pe` com o valor de `lnk_d`. Se a sequência de consulta `pe` tiver um valor diferente na ocorrência, essa dimensão não coletará dados.

Se desejar enviar dados para essa dimensão usando o AppMeasurement, envie uma solicitação de imagem [`tl()`](/help/implement/vars/functions/tl-method.md) com um argumento de tipo de link de `"d"`. Preencha o argumento do nome do link com o valor desejado.

## Itens de dimensão

Como essa variável se baseia em uma sequência personalizada na implementação, sua organização determina quais são os itens de dimensão. A Adobe recomenda agrupar links em categorias relevantes com base nas suas necessidades de relatórios.
