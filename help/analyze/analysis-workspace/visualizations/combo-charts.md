---
description: Permite visualizar facilmente os dados de comparação no Analysis Workspace, como criar comparações com o mês passado, o ano passado e assim por diante.
title: Visualização de gráficos de combinação
feature: Visualizations
role: User, Admin
source-git-commit: e2cd08ae4109e037f8b54edf21239fa6fa659896
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 32%

---


# Gráfico de combinação

>[!NOTE]
>
>Esta funcionalidade está atualmente em [testes limitados](/help/release-notes/releases.md).

O [!UICONTROL Gráfico de combinação] A visualização facilita a criação rápida de uma visualização de comparação sem precisar criar uma tabela primeiro. Você pode ver tendências facilmente em seus dados em uma combinação de linha/barra.

Use um [!UICONTROL Gráfico de combinação] para

* Comparar os pedidos desta semana com pedidos ao mesmo tempo do mês passado (e do ano passado) - tudo dentro de alguns cliques.

* Analise e compare várias métricas rapidamente (como [!UICONTROL Visitantes únicos] e [!UICONTROL Receita]) entre si no mesmo gráfico.

* Analise uma métrica em relação a uma função (como [!UICONTROL Média acumulada]) ao longo de um horizonte temporal.

Lembre-se de que você pode

* Adicionar várias comparações em uma única [!UICONTROL Gráfico de combinação].
* Se você adicionar uma ou mais comparações, elas devem ser do mesmo tipo, como Período de tempo.
* Você pode adicionar até 5 comparações.
* Você pode aplicar um filtro a uma métrica.

## Criar um gráfico de Combinação

1. Na lista suspensa Visualizações , no painel à esquerda, arraste a [!UICONTROL Gráfico de combinação] visualização em um painel em branco.

   ![](assets/combo-chart-build.png)

1. Nas listas suspensas, selecione uma dimensão para o eixo X e uma métrica para o eixo Y.

1. Selecione o tipo de [!UICONTROL Comparação de linhas] você deseja usar.

   | Tipo de comparação de linha | Definição |
   | --- | --- |
   | Período | O tipo de comparação mais comum - comparando esse período com 4 semanas atrás, por exemplo. Se você selecionou Período, faça uma seleção secundária sobre qual período deseja comparar.<p>![](assets/combo-time-period.png) |
   | Métrica adicional | Você pode, por exemplo, comparar [!UICONTROL Receita] para outra métrica.<p>![](assets/combo-2metrics.png) |
   | Função | Você poderia apresentar uma função como [!UICONTROL Média] na comparação. Consulte uma lista de funções suportadas abaixo.<p>![](assets/combo-functions.png) |

   {style=&quot;table-layout:auto&quot;}

1. Clique em **[!UICONTROL Criar]**.

   A saída será semelhante a esta:

   ![](assets/combo-output.png)

   O período atual é mostrado no gráfico de barras e o período de comparação é representado pelo gráfico de linhas. Os pontos no gráfico de linha são conhecidos como &quot;barras&quot;.

## Funções suportadas

Se você escolher **[!UICONTROL Função]** como [!UICONTROL Tipo de comparação de linha], uma função da métrica escolhida será retornada.

| Função | Definição |
| --- | --- |
| **[!UICONTROL Média acumulada]** | Retorna a média das últimas N linhas. |
| **[!UICONTROL Soma]** | Adiciona todos os valores numéricos de uma métrica em uma coluna (nos elementos de uma dimensão) |
| **[!UICONTROL Expoente]** | Retorna *e* elevado à potência de um número especificado. |
| **[!UICONTROL Média]** | Retorna a média aritmética, ou média, de uma métrica. |
| **[!UICONTROL Quartil]** | Retorna o quartil de valores de uma métrica. Por exemplo, os quartis podem ser usados para encontrar a porcentagem de 25% dos produtos com maior receita. |

{style=&quot;table-layout:auto&quot;}

Este é um exemplo da média cumulativa da métrica Receita:

![](assets/combo-cumul-avg.png)

Este é um exemplo de um gráfico de combinação com as funções Média cumulativa e Média:

![](assets/combo-two-functions.png)

## Configurações do gráfico de combinação

Clique no ícone de engrenagem na parte superior direita de um gráfico de combinação para alterar suas configurações.

![](assets/combo-settings.png)

| Configuração | Definição |
| --- | --- |
| **[!UICONTROL Geral]** |  |
| **[!UICONTROL Porcentagens]** | Exibe os valores em porcentagens. |
| **[!UICONTROL Legenda visível]** | Permite ocultar o texto detalhado da legenda para a visualização dos Gráficos de combinação. |
| **[!UICONTROL Granularidade]** | Para visualizações de tendências, você pode alterar a granularidade de tempo (dia, semana, mês etc.) nesta lista suspensa. |
| **[!UICONTROL Sobreposições]** | Mostrar ou ocultar os sinalizadores de barras nas linhas. |
| **[!UICONTROL Eixo]** |  |
| **[!UICONTROL Exibir eixo duplo]** | Somente se aplica se você tiver duas métricas. Você pode ter um eixo Y à esquerda (para uma métrica) e outro à direta (para a outra métrica). Isso é útil quando métricas projetadas têm magnitudes muito diferentes. |
| **[!UICONTROL Normalização]** | Força as métricas para proporções iguais. Isso é útil quando métricas projetadas têm magnitudes muito diferentes. |
| **[!UICONTROL Mostrar eixo x]** | Exiba o eixo x ou oculte-o. |
| **[!UICONTROL Mostrar eixo y]** | Exiba o eixo y ou oculte-o. |
| **[!UICONTROL Âncora do eixo y em zero]** | Se todos os valores exibidos no gráfico forem consideravelmente superiores a zero, o padrão do gráfico tornará a parte inferior do eixo y DIFERENTE DE ZERO. Se marcar esta caixa, o eixo y será forçado a zero (e o gráfico será redesenhado). |

{style=&quot;table-layout:auto&quot;}


