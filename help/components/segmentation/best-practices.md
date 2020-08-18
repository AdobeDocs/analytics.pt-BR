---
title: Práticas recomendadas de segmentação
description: Crie segmentos ideais que retornam dados com eficiência.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---


# Práticas recomendadas de segmentação

Segmentos complexos geralmente são necessários para obter os dados desejados. Se os segmentos complexos forem ineficientes e usados em um conjunto de relatórios grande, a execução dos relatórios levará consideravelmente mais tempo. Considere os seguintes recursos ao criar ou editar um segmento para minimizar a complexidade.

## Usar somente o operador &#39;Contém&#39; como último recurso

O operador &quot;Contém&quot; é um dos recursos de processamento mais intenso na segmentação, pois precisa analisar todo o conteúdo de cada valor. Considere o uso de outros operadores, como &quot;Start com&quot; ou &quot;Termina com&quot;, se os valores desejados estiverem no início ou no fim de uma string.

Se um operador &quot;Contém&quot; em um segmento retornar um grande número de resultados, o tempo limite do relatório normalmente é excedido. Por exemplo, se você criou um segmento em que `Referrer equals "."`, o segmento pesquisa o conteúdo de cada valor. Considere usar o operador &quot;Existe&quot;.

## Usar classificações para agrupar itens de dimensão

Se você tiver muitas condições de segmento, elas podem degradar rapidamente o desempenho do segmento. Por exemplo, `Page equals X or Page equals Y or Page equals Z` repetido com centenas de valores diferentes. Em vez de anotar essas centenas de condições, classifique todos os valores desejados em um segmento e use o valor classificado em um segmento.

1. Crie uma classificação para a variável com a qual você está trabalhando.
2. Baixe o modelo de classificação e abra-o no editor de planilha ou texto desejado.
3. Atribua o mesmo valor a cada item de dimensão que você gostaria de incluir no seu segmento.
4. Use o importador de classificação para importar a planilha de volta para o Adobe Analytics
5. Quando a classificação terminar de processar, crie um segmento usando o valor classificado.

Esse método aumenta drasticamente o desempenho e fornece uma maneira fácil de modificar as condições do segmento. Em vez de editar o segmento com valores diferentes, você pode adicionar ou remover itens de dimensão da classificação.
