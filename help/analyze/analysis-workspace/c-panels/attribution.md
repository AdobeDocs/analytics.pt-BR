---
title: Painel de atribuição
description: Como usar e interpretar o painel de atribuição no Analysis Workspace.
translation-type: tm+mt
source-git-commit: 7962e7dbb8003103ceb6fd1f9ccd11c110e59ad3
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 66%

---


# Painel de atribuição

The [!UICONTROL Attribution] panel is an easy way to build an analysis comparing various attribution models. É um recurso no [Attribution IQ](../attribution/overview.md) que oferece um espaço de trabalho dedicado para usar e comparar modelos de atribuição.

## Criar um painel de atribuição

1. Clique no ícone do painel à esquerda.
1. Drag the [!UICONTROL Attribution] panel into your Analysis Workspace Project.

   ![Novo painel de atribuição](assets/Attribution_Panel_1.png)

1. Adicione uma métrica que você deseja atribuir e adicione qualquer dimensão ao atributo. Os exemplos incluem Canais de marketing ou dimensões personalizadas, como promoções internas.

   ![Selecionar dimensão e métrica](assets/attribution_panel2.png)

1. Selecione os [modelos de atribuição e a janela de pesquisa](../attribution/models.md) que você deseja comparar.

1. O painel Atribuição retorna um conjunto avançado de dados e visualizações que comparam a atribuição da dimensão e da métrica selecionadas.

   ![Visualizações de atribuição](assets/attr_panel_vizs.png)

## Visualizações de atribuição

* **Métrica total**: o número total de conversões que ocorreram ao longo da janela de tempo do relatório. Essas são as conversões atribuídas pela dimensão selecionada.
* **Barra** de comparação de atribuição: Compara visualmente as conversões atribuídas em cada um dos itens de dimensão da dimensão selecionada. Cada cor da barra representa um modelo de atribuição distinto.
* **Tabela** de comparação de atribuição: Mostra os mesmos dados que o gráfico de barras, representado como uma tabela. Selecionar diferentes colunas ou linhas nesta tabela filtra o gráfico de barras, bem como várias outras visualizações no painel. Esta tabela atua de forma semelhante a qualquer outra Tabela de forma livre no Workspace - permitindo adicionar componentes como métricas, segmentos ou detalhamentos.
* **Diagrama** de sobreposição: Um diagrama Venn mostrando os três principais itens de dimensão e a frequência com que eles participam em conjunto em uma conversão. Por exemplo, o tamanho da sobreposição entre as bolhas indica com que frequência as conversões ocorreram quando um visitante foi exposto a ambos os itens de dimensão. Selecionar outras linhas na tabela de Forma livre adjacente atualizará a visualização para refletir a seleção.
* **Detalhes** do desempenho: Permite comparar até três modelos de atribuição visualmente usando um gráfico de dispersão.
* **Desempenho** com tendência: Mostra a tendência de conversões atribuídas para o item de dimensão superior. Selecionar outras linhas na tabela de Forma livre adjacente atualizará a visualização para refletir a seleção.
* **Fluxo**: Permite que você veja com quais canais interagem mais comumente, e em que ordem, ao longo de uma jornada de visitantes.

