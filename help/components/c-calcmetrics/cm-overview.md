---
description: Métricas calculadas e métricas calculadas avançadas são métricas personalizadas que podem ser criadas a partir de métricas existentes.
keywords: Métricas calculadas;métricas calculadas avançadas
title: Métricas calculadas e métricas calculadas avançadas
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 9714863374052e257e1d6349c442fc74182a0a2f
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 100%

---

# Métricas calculadas e métricas calculadas avançadas

Métricas calculadas e métricas calculadas avançadas são métricas personalizadas que podem ser criadas a partir de métricas existentes.

Nossas ferramentas para métricas calculadas oferecem uma maneira muito mais flexível para criar, gerenciar e preparar métricas. Elas permitem que os profissionais de marketing, gerentes de produtos e analistas façam perguntas sobre os dados sem precisarem alterar a implementação do [!DNL Analytics]. As métricas personalizadas disponíveis em cada pacote do [!DNL Analytics] são:

* Adobe [!DNL Analytics] Foundation: calculadas
* [Adobe Analytics Select](https://www.adobe.com/br/data-analytics-cloud/analytics/select.html): Calculadas + Calculadas avançadas
* [Adobe Analytics Prime](https://www.adobe.com/br/data-analytics-cloud/analytics/prime.html): Calculadas + Calculadas avançadas
* [Adobe Analytics Ultimate](https://www.adobe.com/br/data-analytics-cloud/analytics/ultimate.html): Calculadas + Calculadas avançadas

Confira abaixo uma comparação entre os recursos de métricas calculadas e métricas calculadas avançadas:

| Opções do criador | Métricas calculadas | Métricas calculadas avançadas |
|---|---|---|
| [Tipos de formatos (decimal, hora, percentual, moeda)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | Sim | Sim |
| [Alterações de atribuição (padrão, linear, participação etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sim | Sim |
| [Tipos de métrica (padrão, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sim | Sim |
| Operadores básicos (adição, subtração, multiplicação, divisão) | Sim | Sim |
| [Aplicar segmentos](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | Não | Sim |
| [Funções básicas (contagem, valor absoluto, meio etc.)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | Não | Sim |
| [Funções avançadas (regressão, if/then, t-score etc.)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | Não | Sim |

## Capacidades {#section_A0A5C275B68A4D628950BBB0B1EE631F}

É possível

* Crie métricas em [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Detecção de anomalias] e [!UICONTROL Análise de contribuição].
* Criar métricas segmentadas derivadas do tempo de execução do relatório, sem precisar alterar a implementação. Essas métricas podem ser exibidas historicamente, pois se baseiam em segmentos.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas](https://video.tv.adobe.com/v/32608?quality=12&learn=on&captions=por_br){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

* Compartilhe métricas em conjuntos de relatórios. Isso significa que todas as métricas recém-criadas se aplicam a todos os conjuntos de relatórios da mesma empresa de logon.
* (Somente métricas calculadas avançadas) Segmente nas métricas. Por exemplo, é possível criar uma métrica para “Novos visitantes” com uma contagem de pessoas para as quais esta é a primeira sessão.

* (Somente métricas calculadas avançadas) Incorpore funções estatísticas para ajudar a descrever melhor os seus dados. Por exemplo, é possível contar o número de itens em um relatório ou adicionar o número de desvios padrão para cada item.


## Limitações

Alguns recursos do [!DNL Analytics] permitem usar eventos, mas não permitem usar métricas calculadas:

* [!UICONTROL Fallout] na [!UICONTROL Analysis Workspace]
* [!UICONTROL Análise de coorte] na Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segmentos]
* [!DNL Analytics] for [!DNL Target]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas](https://video.tv.adobe.com/v/32608?quality=12&learn=on&captions=por_br){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas segmentadas em segmentos](https://video.tv.adobe.com/v/32603?quality=12&learn=on&captions=por_br){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->