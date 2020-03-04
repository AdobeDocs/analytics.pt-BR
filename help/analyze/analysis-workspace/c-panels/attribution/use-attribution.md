---
title: Usar o Attribution no Analysis Workspace
description: Saiba mais sobre os locais no Adobe Analytics onde você pode usar atribuição.
translation-type: tm+mt
source-git-commit: 509f86a0346e909b62d237deea71c67b7ee950af

---


# Usar o Attribution no Analysis Workspace

O Attribution IQ no Analysis Workspace permite comparar quaisquer modelos de atribuição compatíveis entre si, visualizar as principais sequências de marketing que geram conversões com visualizações avançadas de fallout e de fluxo, colocar em tendência qualquer canal de marketing ou campanha para exibir seu desempenho ao longo do tempo, encontrar anomalias de estatística no desempenho d canal/campanha e ser alertado quando há uma queda ou aumento no desempenho.

## Usar atribuição em tabelas de forma livre {#section_F2F72AE840EB4EA781302A559726E6F4}

Tabelas de forma livre do Analysis Workspace suportam modelos de atribuição que podem ser usados em quase qualquer métrica. Modelos de atribuição podem ser definidos em uma métrica de coluna de Tabela de forma livre nas Configurações de coluna:

1. Clique no ícone de Configurações (engrenagem) em uma coluna de Tabela de forma livre.

   ![](assets/Column_Settings.png)

1. Em **[!UICONTROL Data Settings]**, verifique **[!UICONTROL Use non-default attribution model]**. Para obter mais informações sobre os diferentes modelos de atribuição, consulte [Visão geral do Attribution IQ](attribution.md).

   ![](assets/Attribution_Model_Selection.png)

## Aplicar modelos de atribuição a detalhamentos {#section_ED1E7532CF084B5AB0942BD80B4770C9}

Qualquer detalhamento em uma Tabela de forma livre também pode ter qualquer modelo de atribuição aplicado a ele, podendo ser o mesmo ou um diferente da coluna principal. Por exemplo, se você desejar analisar Pedidos lineares em sua dimensão de Canais de marketing mas deseja aplicar Pedidos de forma de U aos códigos de rastreamento específicos em um Canal. Para editar o modelo de atribuição aplicado a um detalhamento, passe o mouse sobre o modelo de detalhamento e clique em “Editar”:

![](assets/breakdown_settings.png)

## Comparar um modelo de atribuição a outro {#section_1D74C09549CC4EC8A952A7392C76D375}

If you&#39;d like to quickly and easily compare one attribution model to another, right click a metric and select **[!UICONTROL Add comparative attribution model]**:

![](assets/Comparative_Attribution_Model.png)

Isso permite que você compare dois modelos de atribuição sem precisar arrastar uma métrica e configurá-la duas vezes.

## Painel de atribuição e visualizações {#section_6B02F28182F14ECC9FC5020F224726E6}

O painel de atribuição é uma maneira fácil para criar uma análise comparando vários modelos de atribuição. Para acessar o Painel de atribuição,

1. Clique no ícone do painel localizado na extrema esquerda.
1. Arraste o Painel de atribuição para seu projeto do Analysis Workspace.

   ![](assets/Attribution_Panel_1.png)

1. Adicione uma métrica de sucesso que você deseja atribuir e adicione uma dimensão de canal para a qual atribuir (como Canais de marketing ou Promoções internas).

   ![](assets/attribution_panel2.png)

1. Selecione os [modelos de atribuição](attribution.md) que você deseja comparar e a janela de retrospectiva.

   O Painel de atribuição retornará um conjunto avançado de dados e visualizações para ajudá-lo a compreender como seus Canais de marketing (ou outras dimensões) trabalham juntos:

   ![](assets/attr_panel_vizs.png)

   Veja a seguir uma descrição de cada visualização:

| Visualização | Descrição |
|--- |--- |
| Métrica total | O número total de conversões que ocorreram ao longo da janela de tempo de relatório. Essas são as conversões atribuídas pela dimensão selecionada. |
| Gráfico de barras de comparação de atribuição de métricas | Permite comparar visualmente as conversões atribuídas entre cada um dos itens de dimensão a partir da dimensão selecionada. A cor de cada barra representa um modelo de atribuição distinto que foi selecionado. |
| Tabela de forma livre de atribuição de métricas | Mostra os mesmos dados que o gráfico de barras. Selecionar diferentes colunas ou linhas nessa tabela filtra o gráfico de barras bem como várias outras visualizações no painel. Essa tabela age como qualquer outra Tabela de forma livre no Workspace, permitindo adicionar métricas, segmentos, detalhamentos etc. |
| Gráfico de sobreposição de dimensões | Um diagrama de Venn exibindo os três itens de dimensão principais (por exemplo, Canais) e a frequência com a qual participam juntos em uma conversão. Por exemplo, o tamanho da sobreposição entre as bolhas indica com que frequência as conversões ocorreram quando um visitante foi exposto a ambos os itens de dimensão (ex: Canais). Selecionar outras linhas na tabela de Forma livre atualizará a visualização para refletir sua seleção. |
| Pontos de contato de marketing por jornada | Um Histograma que indica o número de pontos de contato de marketing (ou qualquer outra dimensão) de um visitante no intervalo de datas de relatório. Isso é útil para descobrir o impacto da atribuição de multi toque em seu conjunto de dados. Se quase todos os visitantes tiverem somente um ponto de contato, diferentes modelos de atribuição não terão resultados muito diferentes. |
| Detalhes de desempenho de canal de marketing | Permite comparar até três modelos de atribuição visualmente usando um gráfico de dispersão. |
| Fluxo de canal de marketing | Permite ver em quais canais há mais interação e em que ordem isso ocorre na jornada de um visitante. |
