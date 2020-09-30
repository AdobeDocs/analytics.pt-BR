---
description: Você pode ver e analisar anomalias de dados de forma contextual no Analysis Workspace.
title: Visão geral da Detecção de anomalias
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 56ca9fa36db9d7dd126808280ba17f29f4b787d9
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 90%

---


# Visão geral da Detecção de anomalias

Você pode ver e analisar anomalias de dados de forma contextual no Analysis Workspace.

[Tutorial](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html) em vídeo da Detecção de anomalias (4:53)

[Tutorial](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/data-science/contribution-analysis-workspace.html) em vídeo Análise de contribuição (3:20)

>[!IMPORTANT]
>
>A Detecção de anomalias foi removida do conjunto de recursos do Reports &amp; Analytics e agora está disponível apenas por meio da Analysis Workspace. Observe que os clientes do Adobe Analytics Select e do Adobe Analytics Foundation só têm acesso à Detecção de anomalias de “granularidade diária” no Workspace. Para obter mais informações, consulte [Direitos de Detecção de anomalias e Análise de contribuição](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A).

A Detecção de anomalias oferece um método estatístico para determinar como uma certa métrica foi alterada com relação aos dados anteriores.

A Detecção de anomalias permite separar os &quot;sinais verdadeiros&quot; do &quot;barulho&quot; e identificar possíveis fatores que contribuem para os sinais ou as anomalias. Em outras palavras, ele permite identificar quais flutuações estatísticas importam ou não. Assim, você pode identificar a causa raiz de uma verdadeira anomalia. Além disso, é possível obter previsões de métrica confiáveis (KPI).

Exemplos de anomalias que você pode investigar incluem:

* Quedas drásticas no valor médio de pedido
* Picos em pedidos com receita baixa
* Picos ou quedas em registros de avaliação
* Quedas em visualizações da página inicial
* Picos em eventos de buffer de vídeo
* Picos em taxas de vídeo baixas

A Detecção de anomalias e a [Análise de contribuição](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) são fluxos de trabalho principais no Analysis Workspace. Você pode executar a Análise de contribuição em relação a qualquer anomalia diária e incorporar o resultado ao projeto do Analysis Workspace.

O algoritmo de detecção de anomalias do Analysis Workspace inclui

* Oferece suporte para granularidade horária, semanal e mensal, além da granularidade diária existente.
* Oferece conscientização de sazonalidade (como “Black Friday”) e feriados.
