---
description: Saiba mais sobre visualizações e configurações de exibição no Analysis Workspace.
keywords: Analysis Workspace
title: Visão geral das visualizações
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# Visão geral das visualizações

O Workspace oferta várias visualizações que permitem gerar representações visuais de seus dados, como gráficos de barras, gráficos de rosca, histogramas, gráficos de linha, mapas, gráficos de dispersão e outros. Cada visualização tem suas próprias configurações que podem ser gerenciadas. Clique no nome da visualização para obter informações mais detalhadas.

Vídeo do YouTube: Tipos de [visualização na área de trabalho](https://www.youtube.com/watch?v=b1zLEywRa6w&amp;index=39&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) da Análise (2:57)

| Nome da visualização | Descrição |
|---|---|
| [Área](/help/analyze/analysis-workspace/visualizations/area.md) | como um gráfico de linhas, mas com uma área colorida abaixo da linha. Use um gráfico de área quando tiver várias métricas e quiser visualizar a área expressa pela interseção de duas ou mais métricas. |
| [Barra](/help/analyze/analysis-workspace/visualizations/bar.md) | Mostra barras verticais que representam vários valores em uma ou mais métricas. |
| [Gráfico em marcadores](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | Mostra como um valor de seu interesse se compara ou mede em relação a outros intervalos de desempenho (metas). |
| [Tabela de coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | A *`cohort`* é um grupo de pessoas com características comuns em um período específico. A análise de coorte é útil, por exemplo, quando você deseja saber como uma coorte interage com uma marca. Você pode detectar facilmente as mudanças nas tendências e atuar de acordo com elas. |
| [Rosca](/help/analyze/analysis-workspace/visualizations/donut.md) | Semelhante a um gráfico de pizza, essa visualização mostra dados como partes ou segmentos de um todo. |
| [Fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | Os relatórios de fallout mostram onde os visitantes saíram e continuaram em uma sequência predefinida de páginas. |
| [Fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | Mostra os caminhos do cliente pelos sites e aplicativos. |
| [Tabela de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table.md) | Uma tabela de forma livre não é apenas uma tabela de dados, mas também uma visualização interativa. |
| [Histograma](/help/analyze/analysis-workspace/visualizations/histogram.md) | Um histograma é semelhante a um gráfico de barras, mas agrupa números em intervalos (grupos). |
| [Barra horizontal](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | Mostra barras horizontais que representam vários valores em uma ou mais métricas. |
| [Linha](/help/analyze/analysis-workspace/visualizations/line.md) | Representa métricas que usam uma linha para mostrar como os valores mudam em um período de tempo. Um gráfico de linha pode ser usado somente quando o tempo é usado como uma dimensão. |
| [Mapa](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | Permite criar um mapa visual de qualquer métrica (incluindo métricas calculadas). |
| [Gráfico de dispersão](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | Mostra a relação entre valores de dimensão e até três métricas. |
| [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | Dependendo da célula selecionada, essa visualização mostra os totais e os resumos. |
| [Alteração de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | Dependendo das células selecionadas, essa visualização compara as células umas às outras. |
| [Texto](/help/analyze/analysis-workspace/visualizations/text.md) | Permite adicionar texto definido pelo usuário ao Espaço de trabalho. |
| [Mapas de árvore](/help/analyze/analysis-workspace/visualizations/treemap.md) | Exibe dados hierárquicos (estruturados em árvore) como um conjunto de retângulos aninhados. |
| [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) | Permite arrastar até três segmentos (de Componentes) e uma métrica para criar um diagrama Venn. |

## Painel Visualizações {#section_DC07F032FBEF4046A40F7B95C28DA018}

To display the Visualizations panel, click **[!UICONTROL Visualizations]** in the side panel.

![Resultado da etapa](assets/visualizations.png)

A maioria dos tipos de visualização (como gráficos de Área, Barra, Rosca e Linha) será familiar se você usar o Adobe Analytics. Contudo, o Analysis Workspace fornece configurações de visualização e muitos tipos de visualizações exclusivos ou novos com recursos interativos.

## Configurações de visualização {#section_D3BB5042A92245D8BF6BCF072C66624B}

Para acessar [!UICONTROL Visualization Settings], arraste uma visualização para [!UICONTROL Freeform Panel]e clique no ícone de [!UICONTROL Visualization Settings] engrenagem.

>[!IMPORTANT]
>
>As configurações de visualização visíveis dependem do tipo de visualização. Nem todas as configurações se aplicam a todas as visualizações. Além disso, algumas configurações avançadas são exibidas **somente** para visualizações específicas, como as configurações [de](/help/analyze/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477)Histograma.

![](assets/visualization_settings.png)

| Configuração | Descrição |
|--- |--- |
| Porcentagens | Exibe valores em porcentagens. |
| 100% empilhado | Essa configuração em visualizações empilhadas de área ou barra ou em barras empilhadas ou em barra horizontal transforma o gráfico em uma visualização &quot;100% empilhada&quot;. Exemplo: ![](assets/stacked_100_percent.png) |
| Legenda visível | Permite ocultar o texto de detalhes do filtro para a visualização Número do resumo/Alteração do resumo. |
| Limitar itens máximos | Permite limitar o número de itens que uma visualização exibe. |
| Ancorar eixo Y no zero | Se todos os valores representados no gráfico estiverem consideravelmente acima de zero, o padrão do gráfico tornará a parte inferior do eixo y NON-ZERO. Se você marcar essa caixa, o eixo y será forçado a zero (e ele redesenhará o gráfico). |
| Normalização | Força as métricas para proporções iguais. |
| Exibir eixo duplo | Somente se aplica se você tiver duas métricas. Você pode ter um eixo Y à esquerda (para uma métrica) e outro à direta (para a outra métrica). |
| Mostrar anomalias | Melhora gráficos de linha e tabelas de forma livre para exibir anomalias de dados. |

## Ícone “Criar visual” {#section_9C11D9DEDC42413AA53E69A71A509DFC}

If you are not sure which visualization to pick, click the **[!UICONTROL Create Visual]** icon in any table row. Esse ícone aparecerá quando você passar o mouse sobre a linha da tabela. Ao clicar no ícone, o Analysis Workspace é exibido e recomenda uma visualização que se adequaria ao seus dados. Por exemplo, se você tiver até três segmentos selecionados, criará um diagrama Venn. Para mais de três segmentos, criará um gráfico de barras. Para outros tipos de dados, ele pode criar um gráfico de linhas etc.

![](assets/create-visual.png)

## Menu de visualização/painel após clicar com o botão direito {#section_05B7914D4C9E443F97E2BFFDEC70240C}

As configurações contextuais a um gráfico podem ser acessadas ao clicar com o botão direito do mouse ao lado de uma visualização ou cabeçalho do painel. Algumas ou todas as configurações a seguir estarão disponíveis:

![](assets/right-click_menu.png)

| Configuração | Descrição |
|--- |--- |
| Inserir visualização/painel copiados | Permite colar (&quot;inserir&quot;) o elemento copiado em outro lugar dentro do projeto ou em um projeto completamente diferente. |
| Copiar visualização/painel | Permite clicar com o botão direito do mouse e copiar uma visualização ou painel. |
| Visualização de Duplicados/Painel | Faz um duplicado exato da visualização atual, que pode ser modificado. |
| Recolher todos os painéis | Recolhe todos os painéis do projeto. |
| Recolher todas as visualizações no painel | Recolhe todas as visualizações neste painel de projeto. |
| Expandir todos os painéis | Expande todos os painéis do projeto. |
| Expandir todas as visualizações no painel | Expande todas as visualizações neste painel de projeto. |
| Editar descrição | Adicione (ou edite) uma descrição de texto para a visualização/painel. Esta descrição é exibida em Projeto > Informações e configurações do projeto. |
| Obter link do painel | Permite direcionar alguém para um painel específico em um projeto. |
| Obter link de visualização | Permite copiar e compartilhar este link para direcionar outros usuários para esta visualização. Os usuários serão solicitados a fazer logon. |
| Start sobre | (Funciona para Fluxo, Venn, Histograma) Exclui a configuração da visualização atual e abre um novo painel onde você pode reconfigurá-la. |

## Editar rótulos de legenda {#section_94F1988CB4B9434BA1D9C6034062C3DE}

É possível renomear os nomes das séries nas legendas de visualização (Fallout, Área, Área empilhada, Barra, Barra empilhada, Rosca, Histograma, Barra horizontal, Barra horizontal empilhada, Linha, Dispersão e Venn) para ajudá-lo a tornar os visuais mais consumíveis.

A edição de legendas **não** se aplica a: Treemap, Marcador, Alteração ou Número do resumo, Texto, Forma livre, Histograma, Coorte ou Visualizações de fluxo.

Para editar um rótulo de legenda em um gráfico de Linha, por exemplo,

1. Clique com o botão direito do mouse em uma das legendas.
1. Clique em **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. Digite o texto do novo rótulo.
1. Press **[!UICONTROL Enter]** to save.

Temos um [vídeo](https://www.youtube.com/watch?v=mry3vDrTml0&amp;index=61&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) sobre esse tópico.
