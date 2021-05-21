---
title: Frequência de retorno
description: A quantidade de tempo entre a visita atual e a anterior.
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '252'
ht-degree: 100%

---

# Frequência de retorno

A dimensão &quot;Frequência de retorno&quot; mostra a duração entre as visitas de visitantes recorrentes. Quando um visitante retorna ao seu site, a Adobe verifica há quanto tempo a visita anterior foi realizada e classifica a ocorrência no item de dimensão apropriado. Essa dimensão é importante para ajudar a medir o apelo de seu site e a relevância para os visitantes ao longo do tempo. Também pode ajudar a identificar o impacto do conteúdo e das promoções do site nos visitantes.

>[!TIP]
>
>Essa dimensão não inclui visitantes novos.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

Os dados para essa dimensão são definidos na primeira ocorrência da visita e persistem para toda a visita. O valor não pode mudar no meio da visita.

## Itens de dimensão

Os itens de dimensão incluem compartimentos que se baseiam no tempo, dependendo do tempo decorrido desde a visita anterior.

* Menos de 1 dia
* 1 a 3 dias
* 3 a 7 dias
* 7 a 14 dias
* 14 dias a 1 mês
* Mais de 1 mês

## Os itens de dimensão aparecem em compartimentos fora do intervalo de datas do projeto

Quando você define o período de um projeto, é comum ver o atributo de itens de dimensão para visitas fora do período. Por exemplo, um visitante acessa seu site em julho, e retorna duas vezes em um mesmo dia de setembro. A dimensão Frequência de retorno para o mês de setembro mostraria uma visita em &quot;Mais de 1 mês&quot; e uma visita em &quot;Menos de 1 dia&quot;.
