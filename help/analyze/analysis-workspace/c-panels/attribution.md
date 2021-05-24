---
title: Painel de atribuição
description: Como usar e interpretar o painel de atribuição no Analysis Workspace.
feature: Atribuição
role: Business Practitioner, Administrator
exl-id: 96ce3cb9-7753-4ec0-b551-e70a1508e3b7
source-git-commit: c38e20a7f9a295609181cc9435489ac86cda0852
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 72%

---

# Painel de atribuição

O painel [!UICONTROL Atribuição] é uma maneira fácil de criar uma análise comparando vários modelos de atribuição. É um recurso no [Attribution IQ](../attribution/overview.md) que oferece um espaço de trabalho dedicado para usar e comparar modelos de atribuição.

## Criar um painel de atribuição

1. Clique no ícone do painel à esquerda.
1. Arraste o painel [!UICONTROL Atribuição] para seu projeto do Analysis Workspace.

   ![Novo painel de atribuição](assets/Attribution_Panel_1.png)

1. Adicione uma métrica que você deseja atribuir e adicione qualquer dimensão ao atributo. Os exemplos incluem Canais de marketing ou dimensões personalizadas, como promoções internas.

   ![Selecionar dimensão e métrica](assets/attribution_panel2.png)

1. Selecione os [modelos de atribuição e a janela de pesquisa](../attribution/models.md) que você deseja comparar.

1. O painel Atribuição retorna um conjunto avançado de dados e visualizações que comparam a atribuição da dimensão e da métrica selecionadas.

   ![Visualizações de atribuição](assets/attr_panel_vizs.png)

## Visualizações de atribuição

* **Métrica total**: o número total de conversões que ocorreram ao longo da janela de tempo do relatório. Essas são as conversões atribuídas pela dimensão selecionada.
* **Barra de comparação de atribuição**: compara visualmente as conversões atribuídas em cada um dos itens da dimensão selecionada. Cada cor da barra representa um modelo de atribuição distinto.
* **Tabela de comparação de atribuição**: mostra os mesmos dados que o gráfico de barras, mas representados como uma tabela. Selecionar diferentes colunas ou linhas nesta tabela filtra o gráfico de barras, bem como várias outras visualizações no painel. Essa tabela age de forma semelhante a qualquer outra Tabela de forma livre no Workspace - permitindo adicionar componentes como métricas, segmentos ou detalhamentos.
* **Diagrama de sobreposição**: um diagrama Venn mostrando os três principais itens de dimensão e a frequência com que eles participam em conjunto em uma conversão. Por exemplo, o tamanho da sobreposição entre as bolhas indica com que frequência as conversões ocorreram quando um visitante foi exposto a ambos os itens de dimensão. Selecionar outras linhas na tabela de Forma livre adjacente atualizará a visualização para refletir a seleção.
* **Detalhe de desempenho**: permite comparar até três modelos de atribuição visualmente usando um gráfico de dispersão.
* **Desempenho** com tendência: Por padrão, mostra a tendência do desempenho de conversão por modelo de atribuição para a primeira dimensão listada na tabela de Forma livre adjacente. É possível selecionar diferentes linhas de dimensão na tabela de Forma livre para mostrar a tendência das dimensões selecionadas (como Receita total para cada modelo de atribuição para Campanhas sociais e Pesquisa paga). Como alternativa, você pode selecionar células nas colunas para qualquer combinação de métrica e tipo de atribuição na tabela de Forma livre para ver a tendência do desempenho por valor de dimensão para os modelos de atribuição especificados (como Receita total por canal de marketing usando atribuição de Último contato e Primeiro contato).
* **Fluxo**: permite ver com quais canais a interação é mais comum e em que ordem isso acontece na jornada do visitante.
