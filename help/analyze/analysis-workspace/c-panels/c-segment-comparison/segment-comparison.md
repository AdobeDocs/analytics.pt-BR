---
title: Visão geral do painel de comparação de segmentos
description: Saiba como usar o painel de comparação de segmentos, parte do Segment IQ no Analysis Workspace.
keywords: Analysis Workspace;Segment IQ
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 37%

---

# Visão geral do painel de comparação de segmentos {#segment-comparison-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_button"
>title="Comparação de segmentos "
>abstract="Compare rapidamente dois segmentos em todos os pontos de dados para encontrar automaticamente diferenças relevantes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_panel"
>title="Painel de comparação de segmentos"
>abstract="Compare rapidamente dois segmentos em todos os pontos de dados para encontrar automaticamente diferenças relevantes.<br/><br/>**Parâmetros **<br/>**Adicionar um segmento**: o primeiro segmento que você deseja analisar.<br/>**Comparar com**: o segundo segmento com o qual você deseja comparar. Isso será preenchido automaticamente com *Todos os outros*, que é o inverso do seu primeiro segmento. É possível substituir por um segmento diferente, se desejar.<br/>**Configurações avançadas**: a capacidade de excluir componentes de serem analisados na comparação de segmentos."
<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Este artigo documenta o painel de comparação de segmentos no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Não há painel equivalente em_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

O painel de comparação de segmentos é uma ferramenta do [Segment IQ](../../segment-iq.md) que descobre as diferenças estatisticamente mais significativas entre um número ilimitado de segmentos. Esse recurso é repetido por meio de uma análise automatizada de todas as dimensões e métricas a que você tem acesso. A análise descobre as principais características dos segmentos de público-alvo que estão liderando os indicadores de desempenho (KPIs) da sua empresa e permite que você veja o nível de sobreposição entre quaisquer segmentos.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Comparação de segmentos](https://video.tv.adobe.com/v/23976?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]



## Usar

Para usar um painel **[!UICONTROL Atribuição]**:

1. Crie um painel **[!UICONTROL Atribuição]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](../panels.md#create-a-panel).

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.



### Entrada do painel

Você pode configurar o painel [!UICONTROL Comparação de segmentos] usando estas configurações de entrada:

![Painel de entrada de comparação de segmentos](assets/segment-comparison-input.png)

| Entrada | Descrição |
| --- | --- |
| **[!UICONTROL Adicionar um segmento]** | Selecione a dimensão que deseja comparar. |
| **[!UICONTROL Comparar com]** | Selecione a dimensão que deseja usar para comparar o segmento selecionado inicial. Se você não selecionar um segmento específico, o segmento padrão **[!UICONTROL Todos os outros]** será usado. |
| **[!UICONTROL Mostrar/ocultar configurações avançadas]** | Selecione **[!UICONTROL Mostrar configurações avançadas]** para configurar **[!UICONTROL Componentes excluídos]**, selecione **[!UICONTROL Ocultar configurações avançadas]** para ocultar **[!UICONTROL Componentes excluídos]**. |
| **[!UICONTROL Componentes excluídos]** | Componentes que você pode especificar, como **[!UICONTROL Dimension]**, **[!UICONTROL Métricas]** ou **[!UICONTROL Segmentos]** para exclusão.<br><ul><li>Arraste e solte uma ou mais dimensões, métricas ou segmentos dos containers no contêiner **[!UICONTROL Componentes excluídos]**.</li><li>Para remover um componente, selecione o tipo (**[!UICONTROL Dimension]** **[!UICONTROL Métricas]** ou **[!UICONTROL Segmentos]**) e selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover um componente. Para remover todos os componentes, selecione **[!UICONTROL Limpar tudo]**.</li><li>Para definir a seleção atual de dimensões, métricas e segmentos como padrão, selecione **[!UICONTROL Definir como padrão]**.</li></ul> |

Selecione **[!UICONTROL Criar]** para criar o painel.

### Saída do painel

Quando o Adobe Analytics terminar de analisar os dois segmentos desejados, os painéis de saída mostrarão resultados por meio de várias visualizações:

![Comparação de segmentos de saída do painel](assets/segment-comparison-output.png)

| Visualização | Descrição |
|---|---|
| **[!UICONTROL Tamanho e sobreposição]** | Ilustra com uma visualização de [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) os tamanhos comparativos de cada segmento selecionado e o quanto eles se sobrepõem. |
| **[!UICONTROL Visitantes únicos do primeiro segmento]** | Uma visualização [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) mostrando os visitantes únicos para o primeiro segmento (no exemplo Visitas de página única) |
| **[!UICONTROL Visitantes únicos do 2º segmento]** | Uma visualização [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) mostrando os visitantes únicos para o segundo segmento (no exemplo Novas visitas) |
| **[!UICONTROL Principais métricas em relação a segmentos]** | Uma [tabela de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) mostrando as métricas principais dos segmentos selecionados. |
| **[!UICONTROL Métrica ao longo do tempo por segmento]** | Uma visualização de [Linha](/help/analyze/analysis-workspace/visualizations/line.md) mostrando as métricas ao longo do tempo para os segmentos selecionados. |
| **[!UICONTROL Principais itens de dimensão em relação a Segmentos]** | Uma [tabela de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) mostrando os itens de dimensão mistos para os segmentos selecionados. |
| **[!UICONTROL itens de Dimension por segmentos]** | Uma visualização de [Barra horizontal](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) mostrando os itens de dimensão por segmento. |
| **[!UICONTROL Principais segmentos em relação a Segmentos]** | Uma [tabela de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) que mostra os principais segmentos em relação aos segmentos. |
| **[!UICONTROL Sobreposição de segmentos]** | Uma visualização de [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) que mostra a sobreposição do segmento. |

Use ![Editar](/help/assets/icons/Edit.svg) para reconfigurar e recriar o painel.


<!--
#### Size and overlap

Illustrates the comparative sizes of each selected segment and how much they overlap with each other using a venn diagram. You can hover over the visual to see how many visitors were in each overlapping or non-overlapping section. You can also right click on the overlap to create a brand new segment for further analysis. If the two segments are mutually exclusive, no overlap is shown between the two circles (typically seen with segments using a hit container).

![Size and overlap](assets/size-overlap.png)

#### Population summaries

To the right of the Size and Overlap visualization, the total unique visitor count in each segment and overlap is shown.

![Population summaries](assets/population_summaries.png)

#### Top metrics

Displays the most statistically significant metrics between the two segments. Each row in this table represents a differentiating metric, ranked by how different it is between each segment. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific metric is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific metric. If a metric is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Metrics added to this table after the segment comparison has finished do not receive a Difference Score.

![Top metrics](assets/top-metrics.png)

#### Metric over time by segment

To the right of the metrics table is a linked visualization. You can click a line item in the table on the left, and this visualization updates to show that metric trended over time.

![Top metrics line](assets/linked-viz.png)

#### Top dimensions

Shows the most statistically significant dimension items across all of your dimensions. Each row shows the percentage of each segment exhibiting this dimension item. For example, this table might reveal that 100% of visitors in 'Segment A' had the dimension item 'Browser Type: Google', whereas only 19.6% of 'Segment B' had this dimension item. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific dimension item is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific dimension item. If a dimension item is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Dimension items added to this table after the segment comparison has finished do not receive a Difference Score.

![Top dimensions](assets/top-dimension-item1.png)

#### Dimension items by segment

To the right of the dimensions table is a linked bar chart visualization. It shows all displayed dimension items in a bar chart. Clicking a line item in the table on the left updates the visualization on the right.

![Top dimensions bar chart](assets/top-dimension-item.png)

#### Top segments

Shows which other segments (other than the two segments selected for comparison) have statistically significant overlap. For example, this table can show that a third segment, 'Repeat Visitors', overlaps highly with 'Segment A' but does not overlap with 'Segment B'. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific segment is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific segment. If a segment is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Segments added to this table after the segment comparison has finished do not receive a Difference Score.

![Top segments](assets/top-segments.png)

#### Segment overlap

To the right of the segments table is a linked venn diagram visualization. It shows the most statistically significant segment applied to your compared segments. For example, 'Segment A' + 'Statistically significant segment' vs. 'Segment B' + 'Statistically significant segment'. Clicking a segment line item in the table on the left updates the venn diagram on the right.

![Top segments venn diagram](assets/segment-overlap.png)

-->
