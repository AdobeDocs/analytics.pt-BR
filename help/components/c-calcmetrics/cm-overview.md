---
description: Métricas calculadas e métricas calculadas avançadas são métricas personalizadas que podem ser criadas a partir de métricas existentes.
keywords: Métricas calculadas;métricas calculadas avançadas
title: Métricas calculadas e métricas calculadas avançadas
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 36%

---

# Visão geral das métricas calculadas

Métricas calculadas e personalizadas que podem ser criadas a partir de métricas existentes.

As métricas calculadas oferecem uma maneira altamente flexível de criar, gerenciar e preparar métricas. A métrica calculada permite que os profissionais de marketing, gerentes de produtos e analistas façam perguntas sobre os dados sem precisarem alterar a implementação do [!DNL Analytics].

Métricas calculadas estão disponíveis em cada pacote [!DNL Analytics]. No entanto, o Adobe Analytics Foundation Pack for Experience Cloud está limitado a métricas calculadas básicas, incluindo [tipos de formato (decimal, hora, porcentagem, moeda)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), [alterações de alocação (padrão, linear, participação etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md), [tipos de métricas (padrão, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) e [operadores básicos](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#operators) (adicionar, subtrair, multiplicar e dividir).


Consulte a [Descrição do Produto Adobe Analytics](https://helpx.adobe.com/br/legal/product-descriptions/adobe-analytics.html) para obter mais informações.

<!--
Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

| [Format types (decimal, time, percent, currency)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Metric types (standard, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Apply segments](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md)  | ![StopCircle](/help/assets/icons/StopCircle.svg)  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/c-calcmetrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

-->

## Capacidades {#section_A0A5C275B68A4D628950BBB0B1EE631F}

É possível

* [Criar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-workflow.md) em [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Detecção de anomalias] e [!UICONTROL Análise de contribuição].
* [Criar métricas segmentadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) derivadas do tempo de execução do relatório, sem precisar alterar a implementação. Por exemplo, você pode criar uma métrica para *Novos visitantes*, com uma contagem de pessoas para as quais esta é a primeira sessão.

* [Compartilhar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md) entre conjuntos de relatórios. Isso significa que todas as métricas recém-criadas se aplicam a todos os conjuntos de relatórios da mesma empresa de logon.

* [Incorpore funções estatísticas](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) para ajudá-lo a descrever melhor seus dados. Por exemplo, é possível contar o número de itens em um relatório ou adicionar o número de desvios padrão para cada item.

## Limitações

Alguns recursos do [!DNL Analytics] não permitem o uso de métricas calculadas:

* [!UICONTROL Fallout] na [!UICONTROL Analysis Workspace]
* [!UICONTROL Análise de coorte] na Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segmentos]
* [!DNL Analytics] for [!DNL Target]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas segmentadas em segmentos](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

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

>[!MORELIKETHIS]
>
>[Criar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-workflow.md)
>>[Criar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)
>>[Usar funções](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-using-functions.md)
>
