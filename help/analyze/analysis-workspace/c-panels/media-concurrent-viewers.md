---
title: Painel Visualizadores simultâneos de mídia
description: Saiba como usar e interpretar o painel Visualizadores simultâneos de mídia no Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: 29575b51-e319-4156-9834-aa0b671afb31
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 95%

---


# Painel de visualizadores simultâneos de mídia {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Visualizadores simultâneos de mídia"
>abstract="Crie um painel para analisar a audiência média por minuto de um conteúdo específico ou ao longo de um período específico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Visualizadores simultâneos de mídia"
>abstract="Analise visualizadores simultâneos ao longo do tempo, visualize o pico de simultaneidade ou faça o detalhamento e compare.<br/><br>**Granularidade**: selecione o período pelo qual exibir visualizadores simultâneos.<br/>**Números de resumo do painel**:<br/>opção para mostrar números de resumo com detalhes de data ou hora para cada linha. O máximo mostra detalhes para a simultaneidade de pico. O mínimo mostra detalhes para o vale.<br/>**Detalhamento de série (opcional)**: divide a visualização por segmentos, dimensões, itens de dimensão ou intervalos de datas. Visualize até 10 linhas por vez. Os detalhamentos são limitados a um único nível."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo é sobre o painel Visualizadores simultâneos de mídia no_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte [Painel Visualizadores simultâneos de mídia](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) para ver a versão do_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** deste artigo._

>[!ENDSHADEBOX]


>[!NOTE]
>
>O painel Público-alvo médio por minuto de mídia está disponível somente para clientes que compraram o complemento Adobe Analytics para mídia de streaming.
>
>Entre em contato com o representante de vendas da Adobe ou com a equipe de conta da Adobe para obter mais informações.
>

O painel **[!UICONTROL Visualizadores simultâneos de mídia]** permite a análise de visualizadores simultâneos ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de detalhar e comparar.  

Você pode analisar visualizadores simultâneos para entender onde ocorreu o pico de simultaneidade ou onde ocorreram quedas para fornecer insights valiosos sobre a qualidade do conteúdo e o engajamento do visualizador. E para ajudar na solução de problemas ou no planejamento de volume ou escala.

No Analysis Workspace, Visualizadores simultâneos é o número de visitantes únicos que visualizam seus fluxos de mídia em um ponto específico do tempo, independentemente do número de sessões.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [painel Visualizadores simultâneos de mídia](https://video.tv.adobe.com/v/330177?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]



## Usar

Para usar um painel **[!UICONTROL Visualizadores simultâneos de mídia]**:

1. Cria um painel **[!UICONTROL Visualizadores simultâneos de mídia]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Selecione uma visualização de dados para o painel que tem componentes configurados no complemento Adobe Analytics para mídia de streaming.

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.

### Entrada do painel

Você pode configurar o painel Visualizadores simultâneos de mídia usando estas configurações de entrada:

| Configuração | Descrição |
|---|---|
| **[!UICONTROL Intervalo de datas do painel]** | O padrão do intervalo de datas do painel é Hoje.  Você pode editá-lo para exibir um único dia ou muitos meses de cada vez. <br> <br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas. |
| **[!UICONTROL Granularidade]** | O padrão de granularidade é Minuto.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se um intervalo de datas e combinação de granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para acomodar todo o intervalo de datas. |
| **[!UICONTROL Números de resumo do painel]** | Para visualizar os detalhes de data ou hora de visualizadores simultâneos, um número de resumo está disponível. O Máximo mostra detalhes para a simultaneidade de pico. O **[!UICONTROL Mínimo]** mostra detalhes para o período de baixa. O padrão do painel mostra somente Máximo, mas você pode alterá-lo para mostrar Mínimo ou Máximo e Mínimo.<br><br>Se você estiver usando detalhamentos, um número de resumo será exibido para cada um. |
| **[!UICONTROL Detalhamento por séries]** | Opcionalmente, é possível detalhar a visualização por filtros, dimensões, itens de dimensão ou intervalos de datas.<br>É possível exibir até 10 linhas por vez. Os detalhamentos são limitados a um único nível.<br>Ao arrastar uma dimensão, os itens de dimensão principais serão selecionados automaticamente com base no intervalo de datas do painel selecionado.<br>Para comparar intervalos de datas, arraste dois ou mais intervalos de datas para o filtro de detalhamento por séries. |

Aqui está um exemplo do painel configurado para granularidade de **[!UICONTROL Minuto]**, com números de resumo de **[!UICONTROL Máximo apenas]**. E detalhado por **[!UICONTROL Outros]**, **[!UICONTROL Tabela]**, **[!UICONTROL Celular]**, **[!UICONTROL Console de jogos]**, **[!UICONTROL Player de mídia]**, **[!UICONTROL Decodificador de sinais]**, **[!UICONTROL Televisão]**.

![A exibição de detalhamento da Série de visualizadores simultâneos de mídia mostrando 7 de 10 dimensões, segmentos ou intervalos de datas.](assets/concurrent-viewers-series-breakdown.png)

### Saída do painel

O painel Visualizadores simultâneos de mídia retorna um gráfico de linha e números de resumo para incluir detalhes do máximo e/ou mínimo de visualizadores simultâneos.  Na parte superior do painel, há uma linha de resumo que serve como lembrete das configurações do painel selecionadas.

A qualquer momento, selecione o ![painel Editar visualizadores simultâneos de mídia](/help/assets/icons/Edit.svg) para editar e recriar o painel.

Se você selecionar um detalhamento por série, uma linha no gráfico de linhas e um número de resumo serão exibidos para cada:

![A saída dos Visualizadores simultâneos de mídia.](assets/concurrent-viewers-output.png)

### Fonte de dados

A única métrica que pode ser usada nesse painel é a de **[!UICONTROL Visualizadores simultâneos]**:

| Métrica | Descrição |
|---|---|
| **[!UICONTROL Visualizadores simultâneos]** | O número de pessoas únicas visualizando seus fluxos de mídia em um momento específico, independentemente do número de sessões. |

Uma tabela de forma livre não está disponível nessa visualização.  Para exibir a fonte de dados, você pode baixá-la do menu de contexto de visualização do gráfico de linhas e selecionar **[!UICONTROL Baixar dados como CSV]**.  Os detalhamentos por séries estão incluídos.

![As opções de saída de Visualizadores simultâneos com a opção “Baixar dados como CSV” realçadas.](assets/concurrent-viewers-download-csv.png)

## Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| Onde está a tabela de forma livre? Como posso ver a fonte de dados? | A tabela de forma livre não está disponível nessa visualização.  Você pode baixar a fonte de dados no menu de contexto do gráfico de linhas e selecionar **[!UICONTROL Baixar dados como CSV]**. |
| Por que minha granularidade mudou? | Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto).  Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo.<br><br>Ao alterar de um intervalo de datas maior para menor, a granularidade será atualizada para o detalhe mais baixo permitido quando o intervalo de datas for alterado. Para exibir uma granularidade mais alta, edite o painel e recrie. |
| Como comparo nomes de vídeos, filtros, tipos de conteúdo e outros? | Para comparar esses itens em uma única visualização, arraste filtros, dimensões ou itens de dimensão específicos no filtro de detalhamento por série.<br><br>A visualização é limitada a 10 detalhamentos.  Para exibir mais de 10, você deve usar vários painéis. |
| Como comparar intervalos de datas? | Para comparar intervalos de data em uma única visualização, use os detalhamentos por séries arrastando dois ou mais intervalos de datas.  Os intervalos de datas substituem o intervalo de datas do painel. |
| Como alterar o tipo de visualização? | Esse painel permite somente a visualização de linha para a série temporal. |
| Posso executar a detecção de anomalias? | Não.  A detecção de anomalias não está disponível para esse painel. |
| Por que usar pessoas únicas em vez de sessões ativas? | O uso de pessoas únicas permite a remoção de picos indesejados nos limites de exibição (onde as sessões terminam e começam ao mesmo tempo). |
| O que significa ter visualizadores simultâneos com maior granularidade do que um minuto? | Com uma granularidade maior que um minuto, visualizadores simultâneos é a soma de visualizadores simultâneos exclusivos para todos os minutos desse intervalo de tempo.  Por exemplo, na granularidade de nível de hora, os visualizadores simultâneos são a soma de visualizadores simultâneos exclusivos para todos os minutos dentro da hora. |
| O painel Espaço de trabalho mostra as mesmas informações que o Relatório de visualizadores simultâneos? | Não.  No Analysis Workspace, a métrica Visualizadores simultâneos é definida como o número de pessoas únicas visualizando seu fluxo de mídia em um momento específico. Independentemente do número de sessões.<br><br>Essa métrica é diferente do relatório do visualizador simultâneo na seção Relatórios, que usa Sessões ativas simultâneas. O uso de contas de pessoas únicas remove picos indesejados nos limites de exibição (onde as sessões terminam e começam ao mesmo tempo). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Criar um painel](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>>[Painel de tempo gasto na reprodução de mídia](media-playback-time-spent.md)
>>[Painel de média de público-alvo por minuto de mídia](average-minute-audience-panel.md)
>
<!--
# Media Concurrent Viewers panel

Customers who have purchased the Streaming Media Collection Add-on can analyze concurrent viewers to understand where peak concurrency occurred or where drop-offs happened to provide valuable insight into the quality of content and viewer engagement, and to help with troubleshooting or planning for volume or scale.

In Analysis Workspace, Concurrent Viewers is the number of unique visitors viewing your media stream(s) at a specific point in time, regardless of the number of sessions.

The Media Concurrent Viewers panel enables analysis of concurrent viewers over time, with details on peak concurrency and the ability to break down and compare.  To access the Media Concurrent Viewers panel, navigate to a report suite with streaming media components enabled. Then, click the panel icon on the far-left and drag the panel into your Analysis Workspace project.

Here is a video overview of this panel:

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

## Panel Inputs {#Input}

You can configure the Media Concurrent Viewers panel using these input settings:

|Setting|Description|
|---|---|
|Panel date range|The panel date range default is Today.  You may edit it to view a single day or many months at a time. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Granularity|The granularity default is Minute. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Panel summary numbers| To see date or time details for concurrent viewers, a summary number is available. The Maximum shows details for peak concurrency. The Minimum shows details for the trough.  The panel default shows Maximum only, but you can change it to show Minimum or both Maximum and Minimum.<br><br>If you are using breakdowns, a summary number is displayed for each.|
|Series breakdown| Optionally, you can break down your visualization by segments, dimensions, dimension items, or date ranges. <br><br>- You may view up to 10 lines at a time. Breakdowns are limited to a single level.<br><br>- When dragging a dimension, the top dimension items will be automatically selected based on the selected panel date range.<br><br>- To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|

### Default view

![Default view](assets/concurrent-viewers-default.png)


### Series breakdown view

![series breakdown view](assets/concurrent-viewers-series-breakdown.png)

## Panel Output {#Output}

The Media Concurrent Viewers panel returns a line chart and summary numbers to include details for the maximum and/or minimum concurrent viewers.  At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, you can edit and rebuild the panel by clicking the edit pencil on the top right.

If you selected series breakdown, a line on the line chart and a summary number is displayed for each:

![concurrent viewers output](assets/concurrent-viewers-output.png)

### Data Source

The only metric that can be used in this panel is Concurrent Viewers:

|Metric|Description|
|---|---|
|Concurrent Viewers| Number of unique visitors viewing your media stream(s) at a specific point in time, regardless of the number of sessions.<br><br>This is different than Concurrent Viewer reporting in the Reports section, which uses Concurrent Active Sessions.  Using unique visitors accounts for removal of unwanted 'spikes' at show boundaries (where sessions are ending and starting at the same time).|

A Freeform table is not available in this view.  In order to view the data source, you may right-click on the line chart and download as a .csv file.  Series breakdowns will be included.


![concurrent viewers output](assets/concurrent-viewers-download-csv.png)

## FAQs {#FAQ}

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?| The Freeform table is not available in this view.  You can download the data source by right-clicking on the line chart and downloading the CSV file.|
|Why did my granularity change?|This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity will be automatically updated to accommodate the full date range.<br><br>When changing from a larger date range to a smaller one, the granularity will be updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.|
|How do I compare video names, segments, content types, etc?|To compare these in a single visualization, drag segments, dimensions, or specific dimension items in the series breakdown filter.<br><br>The view is limited to 10 breakdowns.  To view more than 10, you must use multiple panels.|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges.  These date ranges will override the panel date range.|
|How do I change the visualization type?|This panel only allows for the line visualization for the time series.|
|Can I run anomaly detection?|No.  Anomaly detection is not available for this panel.|
|Why use unique visitors instead of active sessions?|Using unique visitors enables removal of unwanted spikes at show boundaries (where sessions are ending and starting at the same time).|
|What does it mean to have concurrent viewers at higher granularity than minute?|With a granularity larger than a minute, concurrent viewers is the sum of unique concurrent viewers for all minutes within that time range.  For example, at hour-level granularity concurrent viewers is the sum of unique concurrent viewers for all minutes within the hour.|
|Does the workspace panel show the same information as the Concurrent Viewers Report?|No.  In Analysis Workspace, Concurrent viewers is defined as the number of unique visitors viewing your media stream at a specific point in time, regardless of the number of sessions.<br><br>This is different than Concurrent Viewer reporting in the Reports section, which uses Concurrent Active Sessions.  Using unique visitors accounts for removal of unwanted spikes at show boundaries—where sessions are ending and starting at the same time.|

-->
