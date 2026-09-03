---
title: Totais de métricas calculadas
description: Saiba mais sobre os totais de métricas calculadas no Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
TQID: https://experienceleague.adobe.com/3UJF1Hl3nLqjYAiQuvcE4Jpq26MaTgeba5BmnVfvEps
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e318d41c-1d01-4c1e-9b18-1f61d435ceee
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 149
ht-degree: 94%

---

# Totais de métricas calculadas

Quando você exibe os dados na Analysis Workspace, os totais de métrica calculada são exibidos na maioria dos casos. Em alguns casos, não é possível fornecer um total, como quando as linhas do relatório são de formato misto (por exemplo, decimal e moeda).

Quando os totais são exibidos, geralmente são calculados no lado do servidor, o que significa que o total remove a duplicação de métricas como visitas ou visitantes. Em determinadas circunstâncias, as métricas calculadas são geradas no lado do cliente, somando as linhas da tabela, o que significa que o total não remove a duplicação de métricas como visitas ou visitantes. Isso ocorre:

* Quando [linhas estáticas](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) são usadas em tabelas de forma livre e a opção (padrão) **[!UICONTROL Mostrar como soma das linhas atuais]** é selecionada.
* Na [visualização de Donut](/help/analyze/analysis-workspace/visualizations/donut.md), para que os números somem até 100%.

Para obter mais informações sobre totais no Analysis Workspace, acesse [Totais do Workspace](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total).
