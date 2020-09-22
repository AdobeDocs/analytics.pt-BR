---
title: Java ativado
description: Determina se o Java está ativado no navegador.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '216'
ht-degree: 100%

---


# Java ativado

A dimensão “Java ativado” determina se o navegador tem o Java ativado no momento. É útil nos casos em que você deseja introduzir a funcionalidade baseada em Java no seu site e deseja saber quantos visitantes já têm o Java ativado. Para aqueles que têm o Java desativado, você pode fornecer uma alternativa ou instruções sobre como ativá-lo.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`v` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados detectando se o Java está ativado no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), inclua o parâmetro da sequência de consulta `v` que contém “Y” ou “N” se quiser usar essa dimensão.

## Itens de dimensão

Os itens de dimensão são “Ativado”, “Desativado” e “Desconhecido”.

* **Ativado**: o Java está ativado no navegador. A sequência de consulta `v` continha o valor “Y”.
* **Desativado**: o Java está desativado no navegador ou o navegador não é compatível com o Java. A sequência de consulta `v` continha o valor “N”.
* **Desconhecido**: o AppMeasurement não pôde determinar a compatibilidade com o Java. A sequência de consulta `v` não estava presente na solicitação de imagem.
