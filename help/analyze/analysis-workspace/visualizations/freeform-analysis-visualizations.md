---
description: Representar visualmente seus dados com visualizações.
keywords: Analysis Workspace
title: Visão geral das visualizações
feature: Visualizations
role: User, Admin
exl-id: b40aa942-4a08-4ff3-9895-e92f9a187b54
source-git-commit: b53ef727adc563e05403c50d80bbd0c48bb8a054
workflow-type: tm+mt
source-wordcount: '1457'
ht-degree: 99%

---

# Visão geral das visualizações

O Espaço de trabalho oferece várias visualizações que permitem gerar representações visuais de seus dados, como gráficos de barras, gráficos de rosca, histogramas, gráficos de linhas, mapas, gráficos de dispersão e outros. A maioria dos tipos de visualização será familiar se você usar o Adobe Analytics. Contudo, o Analysis Workspace fornece configurações de visualização e muitos tipos de visualizações exclusivos ou novos com recursos interativos.

## Tipos de visualização

Os seguintes tipos de visualização estão disponíveis no Analysis Workspace:

| Nome da visualização | Descrição |
| --- | --- |
| [Área](/help/analyze/analysis-workspace/visualizations/area.md)<p>![Ícone de área](assets/Smock_GraphArea_18_N.svg)</p> | Semelhante a um gráfico de linhas, mas apresenta uma área colorida abaixo da linha. Use um gráfico de área quando você tiver diversas métricas e desejar visualizar a área expressa pela interseção de duas ou mais métricas. |
| [Barra](/help/analyze/analysis-workspace/visualizations/bar.md)<p>![Ícone de barra](assets/Smock_GraphBarVertical_18_N.svg)</p> | Mostra barras verticais que representam vários valores de uma ou mais métricas. |
| [Gráfico em marcadores](/help/analyze/analysis-workspace/visualizations/bullet-graph.md)<p>![Ícone de marcador](assets/Smock_GraphBullet_18_N.svg)</p> | Mostra a comparação ou a medição de um valor em relação a outros intervalos de desempenho (metas). |
| [Tabela de coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)<p>![Ícone da tabela de coorte](assets/Smock_TextNumbered_18_N.svg)</p> | A *`cohort`* é um grupo de pessoas com características comuns em um período específico. A Análise de coorte é útil para análise de retenção, churn ou latência. |
| [Rosca](/help/analyze/analysis-workspace/visualizations/donut.md)<p>![Ícone de rosquinha](assets/Smock_GraphDonut_18_N.svg)</p> | Semelhante ao gráfico de pizza, essa visualização mostra os dados como partes ou segmentos de um todo. |
| [Fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)<p>![Ícone de fallout](assets/Smock_ConversionFunnel_18_N.svg)</p> | Os relatórios de fallout mostram onde os visitantes saíram e continuaram em uma sequência predefinida de páginas. Pode ser definido como sequências eventuais ou exatas |
| [Fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)<p>![Ícone de fluxo](assets/flow-icon.png)</p> | Mostra os percursos exatos do cliente pelos sites e aplicativos. |
| [Tabela de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)<p>![Ícone de tabela de forma livre](assets/Smock_ViewTable_18_N.svg)</p> | Uma tabela de forma livre não é apenas uma tabela de dados, mas também uma visualização interativa. É a base para a análise de dados no Espaço de trabalho. |
| [Histograma](/help/analyze/analysis-workspace/visualizations/histogram.md)<p>![Ícone de histograma](assets/Smock_GraphHistogram_18_N.svg)</p> | Um histograma agrupa visitantes, visitas ou ocorrências em compartimentos com base em um volume de métrica. |
| [Barra horizontal](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md)<p>![Ícone de barra horizontal](assets/Smock_GraphBarHorizontal_18_N.svg)</p> | Mostra barras horizontais que representam vários valores de uma ou mais métricas. |
| [Resumo da métrica principal](/help/analyze/analysis-workspace/visualizations/key-metric.md)<p>![Ícone de métrica principal](assets/key-metric-icon.png)</p> | Mostra a tendência de uma métrica em um único período ou permite comparar o desempenho da métrica em dois períodos. |
| [Linha](/help/analyze/analysis-workspace/visualizations/line.md)<p>![Ícone de linha](assets/Smock_GraphTrend_18_N.svg)</p> | Representa as métricas que usam uma linha para mostrar como os valores se alteram durante um período. Um gráfico de linhas usa o tempo no eixo x. |
| [Mapa](/help/analyze/analysis-workspace/visualizations/map-visualization.md)<p>![Ícone de mapa](assets/map-icon.png)</p> | Permite criar um mapa visual de qualquer métrica (incluindo métricas calculadas). |
| [Gráfico de dispersão](/help/analyze/analysis-workspace/visualizations/scatterplot.md)<p>![Ícone de gráfico de dispersão](assets/Smock_GraphScatter_18_N.svg)</p> | Mostra a relação entre itens de dimensão e até três métricas. |
| [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)<p>![Ícone de número do resumo](assets/summary-number-icon.png)</p> | Mostra a célula selecionada como um número grande. |
| [Alteração de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)<p>![Ícone de alteração do resumo](assets/summary-change-icon.png)</p> | Mostra a alteração entre as células selecionadas como um número grande/porcentagem. |
| [Texto](/help/analyze/analysis-workspace/visualizations/text.md)<p>![Ícone de texto](assets/Smock_Text_18_N.svg)</p> | Permite adicionar texto definido pelo usuário ao Espaço de trabalho Útil para adicionar contexto à análise e aos insights, além de aproveitar as descrições do painel/da visualização |
| [Mapas de árvore](/help/analyze/analysis-workspace/visualizations/treemap.md)<p>![Ícone de mapa de árvore](assets/Smock_GraphTree_18_N.svg)</p> | Exibe dados hierárquicos (estruturados em formato de árvore) como um conjunto de retângulos aninhados. |
| [Venn](/help/analyze/analysis-workspace/visualizations/venn.md)<p>![Ícone de Venn](assets/venn-icon.png)</p> | Usa círculos para descrever a sobreposição de métrica de até três segmentos. |

## Adicionar visualizações a um painel

1. Abra o projeto do Analysis Workspace em que deseja adicionar uma visualização.

1. Use qualquer um dos métodos a seguir para adicionar a visualização:

   ![Adicionar visualização](assets/add-visualization.png)

   * No painel esquerdo, selecione **Visualizações** de ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) e arraste uma visualização até o painel ao qual deseja adicionar a visualização.

   * No painel ao qual você deseja adicionar a visualização, selecione ![AddCircle](/help/assets/icons/AddCircle.svg) e escolha o ícone que representa a visualização que você deseja adicionar. Passe o cursor do mouse sobre o ícone de cada visualização para ver seu nome.

   * Adicione um [painel em branco](/help/analyze/analysis-workspace/c-panels/blank-panel.md) e selecione a visualização que deseja adicionar.

   * No menu de contexto de uma visualização existente no seu projeto do Analysis Workspace, selecione **[!UICONTROL Duplicar visualização]** ou **[!UICONTROL Copiar visualização]**.

   * Use o menu **[!UICONTROL Inserir]** do Workspace para inserir uma visualização.

   * No menu de contexto de uma tabela de forma livre, selecione **[!UICONTROL Visualizar]**. Em seguida, selecione a visualização no submenu. Com base na seleção atual na tabela, o Workspace determina qual visualização oferecer e interpreta os dados para criar a visualização solicitada.

## Legenda

Uma legenda de visualização ajuda a relacionar a data em uma tabela de origem com a série plotada na visualização. A legenda é interativa: é possível selecionar um item de legenda para mostrar/ocultar uma série na visualização, o que é útil se você quiser simplificar os dados que estão sendo visualizados.

Além disso, é possível renomear rótulos de legenda para ajudá-lo a tornar as exibições mais atraentes. Observação: a edição de legendas **não** se aplica a: Treemap, Marcador, Alteração ou Número do resumo, Texto, Forma livre, Histograma, Coorte ou Visualizações de fluxo.

Para editar um rótulo de legenda:

1. Clique com o botão direito do mouse em uma das etiquetas de legenda.
1. Clique em **[!UICONTROL Editar rótulo]**.

   ![Um rótulo de legenda e a opção “Editar rótulo”.](assets/edit-label.png)

1. Digite o texto do novo rótulo.
1. Pressione **[!UICONTROL Enter]** para salvar.



### Configurações 

As configurações de visualização disponíveis dependem da visualização. A tabela abaixo resume as configurações mais comuns. Algumas visualizações têm configurações específicas. Consulte a documentação referente às visualizações para mais detalhes.

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Tipo de visualização]** | Alterar o tipo de visual usado para visualizar os dados. |
| **[!UICONTROL Granularidade]** | Alterar a granularidade de tempo para visualizações de tendências. Essa alteração também se aplica à tabela de fontes de dados. |
| **[!UICONTROL Porcentagens]** | Exibir os valores em porcentagens. |
| **[!UICONTROL 100% empilhada]** | Transformar o gráfico em uma visualização 100% empilhada.  Aplicável somente a uma visualização de área, barras e barras horizontais empilhadas. |
| **[!UICONTROL Legenda visível]** | Mostrar o texto da legenda. |
| **[!UICONTROL Limite máximo de itens]** | Permite limitar a quantidade de itens exibidos em uma visualização. Quando selecionado, define a quantidade máxima de itens. |
| **[!UICONTROL Mostrar anotações]** | Mostrar as anotações feitas nesta visualização. |
| **[!UICONTROL Ocultar título]** | Ocultar o título da visualização. |
| **[!UICONTROL Ancorar o eixo Y em zero]** | Forçar a parte inferior do eixo Y a zero. Se todos os valores exibidos no gráfico forem consideravelmente superiores a zero, o padrão do gráfico tornará a parte inferior do eixo Y diferente de zero. Se esta opção for habilitada, o eixo Y será forçado a zero (e o gráfico será redesenhado). |
| **[!UICONTROL Exibir eixo duplo]** | Exibir os eixos Y esquerdo e direito para duas métricas diferentes. Esta opção só se aplica se você tiver duas métricas. Eixos duplos são úteis quando métricas projetadas têm magnitudes diferentes. |
| **[!UICONTROL Mostrar eixo X]** | Mostrar o eixo X na visualização. |
| **[!UICONTROL Mostrar eixo Y]** | Mostrar o eixo Y na visualização. |
| **[!UICONTROL Mostrar barras nas linhas]** | Mostrar barras na visualização de linha em uma visualização de gráfico de combinação. |
| **[!UICONTROL Normalização]** | Forçar as métricas a proporções iguais. Proporções iguais são úteis quando métricas projetadas têm magnitudes diferentes. |
| **[!UICONTROL Mostrar anomalias]** | Aprimorar os gráficos de linha e tabelas de forma livre, exibindo a detecção de anomalias. A detecção de anomalias em visualizações de linha inclui um valor esperado (linha tracejada) e um intervalo esperado (faixa sombreada). |
| **[!UICONTROL Mostrar previsão]** | Aprimorar os gráficos de linha e tabelas de forma livre, exibindo os valores de previsão.  |
| **[!UICONTROL Mostrar mín.]** | Mostrar o valor mínimo na visualização. |
| **[!UICONTROL Mostrar máx.]** | Mostrar o valor máximo na visualização. |
| **[!UICONTROL Mostrar linha de tendências]** | Mostrar uma linha de tendências na visualização. Quando selecionada, você pode selecionar o tipo de linha de tendência no menu suspenso. |

É possível personalizar as configurações de todas as visualizações criadas. Para obter mais informações, consulte [Preferências do usuário](/help/analyze/analysis-workspace/user-preferences.md).


## Menu de contexto {#right-click}

Use o menu de contexto (disponível por meio da seleção alternativa, como, por exemplo, ao clicar com o botão direito do mouse) em um cabeçalho de visualização para acessar funcionalidades adicionais de uma visualização. Nem todas as opções estão disponíveis para todas as visualizações.

![Configurações de visualização adicionais, com as opções do botão direito do mouse exibidas. As opções serão descritas na próxima seção.](assets/right-click.png)

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Inserir visualização copiada]** | Colar (inserir) uma visualização copiada em outro lugar dentro do projeto ou em um projeto totalmente diferente. |
| **[!UICONTROL Copiar dados para a área de transferência]** | Copiar dados da visualização para a área de transferência. |
| **[!UICONTROL Copiar seleção para a área de transferência]** | Copiar a seleção da visualização para a área de transferência. |
| **[!UICONTROL Baixar itens como CSV (*nome da dimensão*)]** | Baixar os itens de dimensão (até, no máximo, 50 mil) da visualização para o seu dispositivo local. Até 50 mil itens de dimensão para a dimensão selecionada. |
| **[!UICONTROL Copiar visualização]** | Copiar a visualização, para que você possa inseri-la em outro lugar dentro do projeto ou em um projeto totalmente diferente. |
| **[!UICONTROL Baixar dados como CSV]** | Baixa os dados da visualização no dispositivo local. |
| **[!UICONTROL Duplicar visualização]** | Fazer uma duplicata exata da visualização. |
| **[!UICONTROL Editar descrição]** | Adicionar (ou editar) uma descrição em texto para a visualização. Consulte [Texto](text.md). |
| **[!UICONTROL Obter link da visualização]** | Copiar e compartilhar um link diretamente para a visualização. Uma caixa de diálogo “Compartilhar link” exibe o link. Selecione “Copiar” para copiar o link para a área de transferência. |
| **[!UICONTROL Começar de novo]** | Excluir a configuração da visualização atual, para que você possa reconfigurá-la do zero. |


## Configuração

Algumas visualizações (como tabela de coorte, fallout, fluxo e outras) contêm uma caixa de diálogo de configuração para ajudar a criar a visualização. Use a opção ![Editar](/help/assets/icons/Edit.svg) na parte superior da visualização para acessar e alterar a configuração.

![Painel de configuração](assets/configuration.png)

## Visualizar

Se não tiver certeza de qual visualização selecionar, clique em **[!UICONTROL Visualizar]**  ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg) em qualquer linha da tabela de forma livre (disponível ao passar o cursor do mouse). Essa seleção é a maneira mais rápida de adicionar uma visualização. O Analysis Workspace dá um palpite informado de qual visualização se adequaria melhor aso seus dados. Por exemplo, se você tiver uma linha selecionada, ela criará um [gráfico de linhas](line.md) de tendências. Se você tiver três linhas de filtro selecionadas, ela criará um diagrama de [Venn](venn.md).

![Visualização rápida](assets/quick-viz.png)


<!--
## Settings {#settings}

![](assets/settings.png)

| Setting | Description |
| --- | --- |
| Visualization Type | Change the type of visual used to depict the data. |
| Granularity | For trended visualizations, you can change the time granularity (day, week, month, etc.) from this drop-down list. This change also applies to the data source table. |
| Percentages | Displays values in percentages. |
| 100% Stacked | This setting on area stacked, bar stacked or horizontal bar stacked visualizations turns the chart into a "100% stacked" visualization. Example: ![Stacked 100%](assets/stacked_100_percent.png) |
| Legend Visible | Lets you hide the detailed legend text for the Summary Number/Summary Change visualization. |
| Limit Max Items | Lets you limit the number of items that a visualization displays. |
| Anchor Y Axis at Zero | If all the values plotted on the chart are considerably above zero, the chart default will make the bottom of the y-axis NON-ZERO. If you check this box, the y-axis will be forced to zero (and it will re-draw the chart). |
| Normalization | Forces metrics to equal proportions. This is helpful when plotted metrics are of very different magnitudes. |
| Display Dual Axis | Only applies if you have two metrics - you can have a y-axis on the left (for one metric) and on the right (for the other metric). This is helpful when plotted metrics are of very different magnitudes. |
| Show Anomalies | Enhances line graphs and freeform tables by displaying anomaly detection. Anomaly detection in line visualizations includes an expected value (dashed line) and an expected range (shaded band). |

## Legend {#legend}

A visualization legend helps you to relate date in a source table to plotted series in the visualization. The legend is interactive - you can click a legend item to show/hide a series in the visualization. This is helpful if you want to simplify the data being visualized. 

Additionally, you can rename legend labels to help you make visuals more consumable. Note: legend editing does **not** apply to: Treemap, Bullet, Summary Change/Number, Text, Freeform, Histogram, Cohort or Flow visualizations.

To edit a legend label:

1. Right-click one of the legend labels.
1. Click **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. Enter the new label text.
1. Press **[!UICONTROL Enter]** to save.

## Right-click menu {#right-click}

Additional functionality for a visualziation is available by right-clicking on the visualization header. Settings will vary by visualization. Some of the settings available are:

![](assets/right-click.png)

| Setting | Description |
| --- | --- |
| Insert Copied Panel/Visualization|Lets you paste ("insert") a copied panel or visualization to another place within the project, or into a completely different project. |
| Copy Visualization | Lets you right-click and copy a visualization, so that you can insert it to another place within the project, or into a completely different project. |
| [Download items as CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-items) | Download up to 50,000 dimension items for the selected dimension as a CSV. |
| [Download data as CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-data) | Download visualization data source as a CSV. |
| Duplicate Visualization | Makes an exact duplicate of the current visualization, which you can then modify. |
| Edit Description | Add (or edit) a text description for the visualization. |
| Get Visualization Link | Lets you direct someone to a specific visualization within a project. When the link is clicked, the recipient will be required to login before being directed to the exact visualization linked to. |
| Start Over | (Works for Flow, Venn, Histogram) Deletes the configuration for the current visualization so you can re-configure it from scratch. |

## Create Visual icon {#quick-viz}

If you are not sure which visualization to pick, click the **[!UICONTROL Create Visual]** icon in any table row (available on hover). This the the fastest way to add a visualization. Clicking it prompts Analysis Workspace to take an educated guess at which visualization would best fit your data. For example, if you have 1 row selected, it will create a trended line graph. If you have 3 segment rows selected, it will create a Venn diagram. 

![](assets/quick-viz.png)

## Change the scale axis on visualizations

Here is a video overview:

>[!VIDEO](https://video.tv.adobe.com/v/24708/?quality=12)

-->
