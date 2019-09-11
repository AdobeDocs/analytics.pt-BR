---
title: Totais de métricas calculadas
seo-title: Totais de métricas calculadas
description: Saiba como os totais das métricas calculadas diferem nas ferramentas do Analytics
seo-description: Como os totais das métricas calculadas são calculados
translation-type: tm+mt
source-git-commit: 658925799c530b46ff7b56d5d0685af6d9fef1b8

---


# Totais de métricas calculadas

Como os totais da métrica calculada são exibidos entre [!DNL Reports & Analytics] e [!DNL Analysis Workspace]. Esta seção explica as diferenças.

## Totais de métricas calculadas em [!DNL Reports & Analytics]

Ao visualizar relatórios em [!DNL Reports & Analytics], as métricas calculadas sempre são exibidas `n/a` sob o total. Como todas as métricas calculadas são definidas pelo usuário, há muitas circunstâncias em que esse total não faz sentido. Considere o exemplo a seguir:

Sua organização criou a métrica `orders` calculada/ `visits` para determinar a porcentagem de visitas que compraram algo em seu site. Se você trouxe essa métrica para um relatório de produtos, vários produtos são atribuídos a um único pedido. Além disso, vários produtos são atribuídos a uma única visita. Se um total da métrica calculada foi incluído nesse relatório, as seguintes perguntas surgem:

| Pergunta | Resposta |
|---|---|
| A resumir os itens de linha faz sentido? | Não é, pois vários produtos podem ser incluídos em uma única ordem e vários produtos podem ser incluídos em uma única visita. Se os itens de linha foram agregados, o total de pedidos e total de visitas não corresponderia aos pedidos totais e total de visitas. |
| O total de pedidos e total de visitas faz sentido? | Não é, pois o total não corresponde à soma dos itens de linha individuais. Além disso, os pedidos totais e o Total de visitas são métricas calculadas separadamente. |

Como não há um método lógico e concreto para determinar se uma métrica calculada faz sentido no relatório, o total da métrica é omitido totalmente. Se quiser obter um total geral, você pode fazer um dos seguintes:

* Crie uma métrica calculada que inclua as versões totais das métricas que você deseja incluir.
* Crie um relatório de Extração de dados, que pode ser agendado.
* Create a data request within [!DNL ReportBuilder].
* Use [!DNL Analysis Workspace] (veja abaixo).

## Total de métricas calculadas em [!DNL Analysis Workspace]

Quando você exibe dados na Analysis Workspace, os totais da métrica calculada são exibidos na maioria dos casos. Em alguns casos, não é possível fornecer um total, como quando as linhas do relatório são de formato misto (por exemplo, decimal e moeda).

Quando os totais são exibidos, geralmente são calculados no lado do servidor, o que significa que o total de métricas duplicadas como visitas ou visitantes. Em determinadas circunstâncias, as métricas calculadas são geradas pelo lado do cliente resumindo entre linhas da tabela, o que significa que o total não remove métricas como visitas ou visitantes. Isso ocorre:

* Quando [linhas estáticas](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) são usadas em tabelas de forma livre e **[!UICONTROL a opção Mostrar como soma das linhas]** atuais (padrão) é selecionada.
* Na visualização [de Rosca](/help/analyze/analysis-workspace/visualizations/donut.md), para que os números sejam adicionados a 100%.
