---
title: Totais de métricas calculadas
seo-title: Totais de métricas calculadas
description: Saiba como os totais das métricas calculadas diferem nas ferramentas do Analytics
seo-description: Como os totais das métricas calculadas são calculados
translation-type: tm+mt
source-git-commit: 774975605de502b66279888d8dd8ef58989a40de

---


# Totais de métricas calculadas

Como os totais da métrica calculada são exibidos entre os Relatórios e análises [DNL] e [o DNL Analysis Workspace]. Esta seção explica as diferenças.

## Totais de métricas calculadas em [!DNL Reports & Analytics]

Ao visualizar relatórios em [!DNL Reports & Analytics], as métricas calculadas sempre são exibidas `n/a` sob o total. Como todas as métricas calculadas são definidas pelo usuário, há muitas circunstâncias em que esse total não faz sentido. Considere o exemplo a seguir:

Sua organização criou [os pedidos] / [visitas de métricas calculadas] para determinar a porcentagem de visitas que compraram algo em seu site. Se você trouxe essa métrica para um relatório de produtos, vários produtos são atribuídos a um único pedido. Além disso, vários produtos são atribuídos a uma única visita. Se um total da métrica calculada foi incluído nesse relatório, as seguintes perguntas surgem:

| Pergunta | Resposta |
|---|---|
| A resumir os itens de linha faz sentido? | Não é, pois vários produtos podem ser incluídos em uma única ordem e vários produtos podem ser incluídos em uma única visita. Se os itens de linha foram agregados, o total de pedidos e total de visitas não corresponderia aos pedidos totais e total de visitas. |
| O total de pedidos e total de visitas faz sentido? | Não é, pois o total não corresponde à soma dos itens de linha individuais. Além disso, os pedidos totais e o Total de visitas são métricas calculadas separadamente. |

Como não há um método lógico e concreto para determinar se uma métrica calculada faz sentido no relatório, o total da métrica é omitido totalmente. Se quiser obter um total geral, você pode fazer um dos seguintes:

* Crie uma métrica calculada que inclua as versões totais das métricas que você deseja incluir.
* Crie um relatório de Extração de dados, que pode ser agendado.
* Crie uma solicitação de dados no reportbuilder.
* Use a Analysis Workspace (veja abaixo).

## Total de métricas calculadas em [!DNL Analysis Workspace]

Na Analysis Workspace, em determinadas circunstâncias, as métricas calculadas são somadas para exibir um total:

* Quando há linhas [estáticas](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) e [!UICONTROL Calcular os totais, resumindo os valores atualmente em cada opção de coluna] (padrão) é selecionada.
* Na visualização [de Rosca](/help/analyze/analysis-workspace/visualizations/donut.md).
* Na visualização Alteração [de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md).
