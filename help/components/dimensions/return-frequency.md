---
title: Frequência de retorno
description: A quantidade de tempo entre a visita atual e a anterior.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 4%

---


# Frequência de retorno

A dimensão de &quot;Frequência de retorno&quot; mostra a duração entre as visitas de visitantes recorrentes. Quando um visitante retorna ao seu site, a Adobe verifica há quanto tempo a visita anterior foi realizada e classifica a ocorrência no valor de dimensão apropriado. Essa dimensão é importante para ajudar a medir o apelo de seu site e a relevância para os visitantes ao longo do tempo. Também pode ajudar a identificar o impacto do conteúdo e das promoções do site nos visitantes.

>[!TIP] Essa dimensão não inclui visitantes novos.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios contiver dados, essa dimensão funcionará.

Os dados para essa dimensão são definidos na primeira ocorrência da visita e persistem para a totalidade da visita. O valor não pode alterar mid-visit.

## Valores de dimensão

Os valores de dimensão incluem compartimentos baseados em tempo, dependendo do tempo decorrido desde a visita anterior.

* Menos de 1 dia
* 1 a 3 dias
* 3 a 7 dias
* 7 a 14 dias
* 14 dias a 1 mês
* Mais de 1 mês

## Os valores de dimensão aparecem em compartimentos fora do intervalo de datas do projeto

Quando você define o intervalo de datas de um projeto, é comum ver os valores de dimensão atributos para visitas fora do intervalo de datas. Por exemplo, um visitante chega ao seu site em julho e depois volta duas vezes no mesmo dia em setembro. A dimensão de frequência de retorno para o mês de setembro mostraria uma visita em &#39;Mais de 1 mês&#39; e uma visita em &#39;Menos de 1 dia&#39;.