---
title: Totais de métricas calculadas
description: Saiba mais sobre os totais de métricas calculadas no Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 91%

---

# Totais de métricas calculadas [!DNL Analysis Workspace]

Quando você exibe os dados na Analysis Workspace, os totais de métrica calculada são exibidos na maioria dos casos. Em alguns casos, não é possível fornecer um total, como quando as linhas do relatório são de formato misto (por exemplo, decimal e moeda).

Quando os totais são exibidos, geralmente são calculados no lado do servidor, o que significa que o total remove a duplicação de métricas como visitas ou visitantes. Em determinadas circunstâncias, as métricas calculadas são geradas no lado do cliente, somando as linhas da tabela, o que significa que o total não remove a duplicação de métricas como visitas ou visitantes. Isso ocorre:

* Quando [linhas estáticas](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) são usadas em tabelas de forma livre e a opção (padrão) **[!UICONTROL Mostrar como soma das linhas atuais]** é selecionada.
* Na [visualização de Donut](/help/analyze/analysis-workspace/visualizations/donut.md), para que os números somem até 100%.

Para obter mais informações sobre totais no Analysis Workspace, acesse [Totais do Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html#static-row-total).
