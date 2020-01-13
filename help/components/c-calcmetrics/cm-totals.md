---
title: Totais de métricas calculadas
description: Saiba como os totais de métricas calculadas diferem nas ferramentas do Analytics
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Totais de métricas calculadas

A forma como os totais de métricas calculadas são exibidos difere entre [!DNL Reports & Analytics] e [!DNL Analysis Workspace]. Esta seção explica as diferenças.

## Totais de métricas calculadas em [!DNL Reports & Analytics]

Quando você exibe relatórios em [!DNL Reports & Analytics], as métricas calculadas sempre são exibidas `n/a` abaixo do total. Como todas as métricas calculadas são definidas pelo usuário, há muitas circunstâncias nas quais esse total não faz sentido. Considere o exemplo a seguir:

Sua organização criou a métrica calculada `orders` / `visits` para determinar a porcentagem de visitas que compraram algo em seu site. Se você inclui essa métrica em um relatório de produtos, vários produtos são atribuídos a um único pedido. E vários produtos são atribuídos a uma única visita. Se um total de métrica calculada foi incluído neste relatório, surgem as seguintes perguntas:

| Pergunta | Resposta |
|---|---|
| A soma dos itens de linha faz sentido? | Não, pois vários produtos podem ser incluídos em um único pedido e vários produtos podem ser incluídos em uma única visita. Se os itens de linha fossem agregados, o total de pedidos e o total de visitas não corresponderia ao total real de pedidos e de visitas. |
| Receber o total de pedidos e o total de visitas faz sentido? | Não, já que o total não corresponde à soma dos itens de linha individuais. Além disso, o total de pedidos e o total de visitas são métricas calculadas separadamente. |

Como não há método lógico e concreto para determinar se uma métrica calculada faz sentido no relatório, o total da métrica é omitido completamente. Se quiser obter um total geral, você pode executar um dos seguintes procedimentos:

* Crie uma métrica calculada que inclua as versões totais das métricas que você deseja incluir.
* Crie um relatório de Extração de dados, que pode ser programado.
* Criar uma solicitação de dados no [!DNL ReportBuilder].
* Utilizar [!DNL Analysis Workspace] (veja abaixo).

## Totais de métricas calculadas em [!DNL Analysis Workspace]

Quando você exibe os dados na Analysis Workspace, os totais de métrica calculada são exibidos na maioria dos casos. Em alguns casos, não é possível fornecer um total, como quando as linhas do relatório são de formato misto (por exemplo, decimal e moeda).

Quando os totais são exibidos, geralmente são calculados no lado do servidor, o que significa que o total remove a duplicação de métricas como visitas ou visitantes. Em determinadas circunstâncias, as métricas calculadas são geradas no lado do cliente, somando as linhas da tabela, o que significa que o total não remove a duplicação de métricas como visitas ou visitantes. Isso ocorre:

* Quando [linhas estáticas](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) são usadas em tabelas de forma livre e a opção (padrão) **[!UICONTROL Mostrar como soma das linhas atuais]** é selecionada.
* Na [visualização de Donut](/help/analyze/analysis-workspace/visualizations/donut.md), para que os números somem até 100%.
