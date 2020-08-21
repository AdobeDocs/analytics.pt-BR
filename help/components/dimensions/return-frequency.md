---
title: Frequência de retorno
description: A quantidade de tempo entre a visita atual e a anterior.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 71%

---


# Frequência de retorno

A dimensão &quot;Frequência de retorno&quot; mostra a duração entre as visitas de visitantes recorrentes. Quando um visitante retorna ao seu site, o Adobe verifica há quanto tempo a visita anterior foi realizada e classifica a ocorrência no item de dimensão apropriado. Essa dimensão é importante para ajudar a medir o apelo de seu site e a relevância para os visitantes ao longo do tempo. Também pode ajudar a identificar o impacto do conteúdo e das promoções do site nos visitantes.

>[!TIP]
>
>Essa dimensão não inclui visitantes novos.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

Os dados para essa dimensão são definidos na primeira ocorrência da visita e persistem para toda a visita. O valor não pode mudar no meio da visita.

## itens de Dimension

Os itens de Dimension incluem compartimentos baseados em tempo, dependendo do tempo decorrido desde a visita anterior.

* Menos de 1 dia
* 1 a 3 dias
* 3 a 7 dias
* 7 a 14 dias
* 14 dias a 1 mês
* Mais de 1 mês

## itens de Dimension aparecem em grupos fora do intervalo de datas do projeto

Quando você define o intervalo de datas de um projeto, é comum ver os itens de dimensão atributos para visitas fora do intervalo de datas. Por exemplo, um visitante acessa seu site em julho, e retorna duas vezes em um mesmo dia de setembro. A dimensão Frequência de retorno para o mês de setembro mostraria uma visita em &quot;Mais de 1 mês&quot; e uma visita em &quot;Menos de 1 dia&quot;.