---
title: Práticas recomendadas de segmentação
description: Crie segmentos ideais que retornam dados com eficiência.
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '296'
ht-degree: 100%

---

# Práticas recomendadas de segmentação

Segmentos complexos geralmente são necessários para obter os dados desejados. Se os segmentos complexos forem ineficientes e usados em um conjunto de relatórios grande, a execução dos relatórios levará consideravelmente mais tempo. Considere os seguintes recursos ao criar ou editar um segmento para minimizar a complexidade.

## Usar somente o operador “Contém” como último recurso

O operador “Contém” é um dos recursos de processamento mais intensos na segmentação, pois precisa analisar todo o conteúdo de cada valor. Considere o uso de outros operadores, como “Inicia com” ou “Termina com”, se os valores desejados estiverem no início ou no fim de uma string.

Se um operador “Contém” em um segmento retornar um grande número de resultados, o tempo limite do relatório normalmente é excedido. Por exemplo, se você criou um segmento em que `Referrer equals "."`, o segmento pesquisa o conteúdo de cada valor. Considere usar o operador “Existe”.

## Usar classificações para agrupar itens de dimensão

Se você tiver muitas condições de segmento, elas podem degradar rapidamente o desempenho do segmento. Por exemplo, `Page equals X or Page equals Y or Page equals Z` repetido com centenas de valores diferentes. Em vez de anotar essas centenas de condições, classifique todos os valores desejados em um segmento e use o valor classificado em um segmento.

1. Crie uma classificação para a variável com a qual você está trabalhando.
2. Baixe o modelo de classificação e abra-o no editor de planilha ou texto desejado.
3. Atribua o mesmo valor a cada item de dimensão que você gostaria de incluir no seu segmento.
4. Use o importador de classificação para importar a planilha de volta para o Adobe Analytics
5. Quando a classificação terminar de processar, crie um segmento usando o valor classificado.

Esse método aumenta bastante o desempenho e fornece uma maneira fácil de modificar as condições do segmento. Em vez de editar o segmento com valores diferentes, você pode adicionar ou remover itens de dimensão da classificação.
