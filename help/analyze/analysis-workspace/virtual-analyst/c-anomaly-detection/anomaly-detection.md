---
description: Você pode ver e analisar anomalias de dados de forma contextual no Analysis Workspace.
title: Visão geral da Detecção de anomalias
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
feature: Ferramentas de IA
role: Business Practitioner, Administrator
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '282'
ht-degree: 100%

---

# Visão geral da Detecção de anomalias

Você pode ver e analisar anomalias de dados de forma contextual no Analysis Workspace.

[Tutorial em vídeo sobre a Detecção de anomalias](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=pt-BR) (4:53)

[Tutorial em vídeo da Análise de contribuição](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/contribution-analysis-workspace.html?lang=pt-BR) (3:20)

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

A Detecção de anomalias e a [Análise de contribuição](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=pt-BR) são fluxos de trabalho principais no Analysis Workspace. Você pode executar a Análise de contribuição em relação a qualquer anomalia diária e incorporar o resultado ao projeto do Analysis Workspace.

O algoritmo de detecção de anomalias do Analysis Workspace inclui

* Oferece suporte para granularidade horária, semanal e mensal, além da granularidade diária existente.
* Oferece conscientização de sazonalidade (como “Black Friday”) e feriados.
