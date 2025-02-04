---
title: O que é a Análise de coorte e como ela funciona?
description: Saiba mais sobre os dados do seu público-alvo e os divida em grupos relacionados com a Análise de coorte. Saiba mais sobre a análise de coorte no Analysis Workspace.
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: 1ce002a513860ce15dc8a70825d26795fd93eb1d
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 33%

---

# Visão geral da tabela de coorte {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Tabela de coorte"
>abstract="Crie uma visualização de coorte para agrupar usuários com base na conclusão de um evento e analise o engajamento contínuo e o churn ao longo do tempo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Tabela de coorte"
>abstract="Agrupe os usuários com base na conclusão de um evento e, em seguida, analise o engajamento contínuo e o churn ao longo do tempo.<br/><br/>**Parâmetros **<br/>**Critérios de inclusão**: os componentes usados para definir seus coortes de visitantes iniciais.<br/>**Critérios de retorno**: os componentes usados para determinar se um visitante retornou."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta a tabela de Coorte no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte a [Tabela de coorte](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis) da_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** versão deste artigo._

>[!ENDSHADEBOX]



*coorte* é um grupo de pessoas que compartilham características comuns em um período especificado. Uma visualização de ![TabelaDeTexto](/help/assets/icons/TextNumbered.svg) **[!UICONTROL TabelaDeCoorte]** é útil, por exemplo, quando você deseja saber como uma coorte interage com uma marca. Você pode detectar facilmente as mudanças nas tendências e atuar de acordo com elas. (Há explicações sobre a [!UICONTROL análise de coorte] disponíveis na Web, por exemplo, em [Análise de coorte 101](https://pt.wikipedia.org/wiki/Cohort_analysis).)

Após criar um relatório de coorte, você pode preparar seus componentes (dimensões, métricas e filtros específicos) e, em seguida, compartilhá-lo com qualquer pessoa. Consulte [Preparar e compartilhar](/help/analyze/analysis-workspace/curate-share/curate.md).

Exemplos do que você pode fazer com uma [!UICONTROL Tabela de coorte]:

* Lançar campanhas projetadas para estimular uma ação desejada.
* Deslocar o orçamento de marketing no momento certo do ciclo de vida do cliente.
* Reconhecer quando finalizar uma avaliação ou uma oferta para maximizar o valor.
* Obter ideias para o teste A/B em áreas como o estabelecimento de preços, o caminho de atualização, etc.

A [!UICONTROL Tabela de coorte] está disponível para todos os clientes do Customer Journey Analytics com direitos de acesso ao [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Análise de coorte no Analysis Workspace](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>A [!UICONTROL Análise de coorte] não dá suporte a métricas não filtráveis (incluindo métricas calculadas), métricas não inteiras (como Receita) ou Ocorrências. Somente as métricas que podem ser usadas em filtros podem ser usadas na [!UICONTROL Análise de coorte], e só podem ser aumentadas 1 de cada vez.

As tabelas de coorte no Customer Journey Analytics são compatíveis com métricas com base dupla (ou com base numérica). Por exemplo, Purchase.Value (um duplo) pode ser usado como uma Métrica de inclusão/retorno. Além disso, todas as métricas passadas para o Adobe Experience Platform por meio do Analytics Source Connector também são duplicadas.

## Recursos da tabela de coorte

As seções a seguir descrevem os recursos da Análise de coorte, que permitem o controle ajustado das coortes que você está criando.

Para obter informações mais detalhadas sobre como criar uma coorte e executar um relatório de [!UICONTROL Análise de coorte], consulte [Configurar uma tabela de coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Tabela [!UICONTROL Retenção]

A tabela de coorte [!UICONTROL Retenção] retorna pessoas: cada célula de dados mostra o número bruto e a porcentagem de pessoas na coorte que realizaram a ação durante esse período. É possível incluir até 3 métricas e 10 filtros.

![Um relatório de coorte de representação que mostra as unidades e a porcentagem de pessoas na coorte.](assets/retention-report.png)

### Tabela [!UICONTROL Churn]

A tabela de coorte [!UICONTROL Churn] é o inverso da tabela de retenção e mostra as pessoas que abandonaram ou que nunca atenderam aos critérios de retorno da sua coorte ao longo do tempo. É possível incluir até 3 métricas e 10 filtros.

![Uma tabela de churn mostrando unidades e porcentagem de pessoas que não atenderam aos critérios de retorno para uma coorte.](assets/churn-report.png)

### [!UICONTROL Cálculo contínuo]

Você pode calcular a retenção ou o abandono com base na coluna anterior, não na coluna incluída, que é chamada de cálculo acumulado.

![Um relatório de retenção de coorte mostrando cálculos com base em uma coluna de dados anterior.](assets/retention-report-rolling.png)

### Tabela de [!UICONTROL Latência]

Uma tabela de latência mede o tempo decorrido antes e depois da ocorrência do evento de inclusão. A medição da latência é uma excelente ferramenta para análise prévia e posterior. Uma coluna **[!UICONTROL Incluída]** encontra-se no centro da tabela e períodos de tempo anteriores e posteriores ao evento de inclusão são exibidos em ambos os lados.

![Um relatório de Coorte que mostra o tempo decorrido antes e depois de um evento.](assets/retention-report-latency.png)

### Coorte de [!UICONTROL Dimensão personalizada]

Você pode criar coortes com base em uma dimensão selecionada, em vez de coortes com base em tempo (que são o padrão). Use dimensões como a [!UICONTROL Cidade geográfica], [!UICONTROL Canal de marketing], [!UICONTROL campanha], [!UICONTROL produto], [!UICONTROL página], [!UICONTROL região] ou qualquer outra dimensão para mostrar como a retenção é alterada. Com base nos diferentes valores dessas dimensões.

![Um relatório de Coorte que mostra um relatório personalizado com dimensões selecionadas, não a coorte baseada em tempo padrão.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configurar uma tabela de coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>



<!--
A *`cohort`* is a group of people sharing common characteristics over a specified period. [!UICONTROL Cohort Analysis] is useful, for example, when you want to learn how a cohort engages with a brand. You can easily spot changes in trends, then respond accordingly. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

After creating a cohort report, you can curate its components (specific dimensions, metrics, and segments), then share the cohort report with anyone. See [Curate and Share](/help/analyze/analysis-workspace/curate-share/curate.md).

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* Launch campaigns designed to spur a desired action.
* Shift marketing budget at exactly the right time in the customer lifecycle.
* Recognize when to end a trial or an offer, in order to maximize value.
* Gain ideas for A/B testing in areas such as pricing, upgrade path, and so on.

[!UICONTROL Cohort Analysis] is available for all Adobe Analytics customers with access rights to [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cohort analysis in Analysis Workspace](https://video.tv.adobe.com/v/25965?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] does not support non-segmentable metrics (including calculated metrics), non-integer metrics (such as Revenue), or Occurrences. 
>
>Only metrics that can be used in segments can be used in [!UICONTROL Cohort Analysis], and they can only be incremented by >1 at a time. 

## Cohort Analysis capabilities

The following sections describe Cohort Analysis features that allow for fine-tuned control over the cohorts you are building.

For more detailed information about creating a cohort and running a [!UICONTROL Cohort Analysis] report, see [Configure a Cohort Analysis report](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention] Table

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. You can include up to 3 metrics and up to 10 segments.

![](assets/retention-report.png)


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculate rolling retention](https://video.tv.adobe.com/v/25962?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



### [!UICONTROL Churn] Table

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. You can include up to 3 metrics and up to 10 segments.

![](assets/churn-report.png)

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Churn analysis](https://video.tv.adobe.com/v/25966?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


### [!UICONTROL Rolling Calculation]

Lets you calculate retention or churn based on the previous column, not the included column.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Table

Measures the time that has elapsed before and after the inclusion event occurred. This is an excellent tool for pre/post analysis. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Cohort

Create cohorts based on a selected dimension, and not time-based cohorts, which are the default. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

-->
