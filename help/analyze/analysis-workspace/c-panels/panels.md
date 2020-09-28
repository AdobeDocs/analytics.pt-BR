---
description: Um painel é uma coleção de tabelas e visualizações
title: Visão geral dos painéis
translation-type: tm+mt
source-git-commit: f772494e6e3f8b5ab186c5b0c891f4f5043470f9
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 18%

---


# Visão geral dos painéis

A [!UICONTROL panel] is a collection of tables and visualizations. Você pode acessar painéis usando o ícone superior esquerdo no Workspace. Os painéis são úteis quando você deseja organizar seus projetos de acordo com períodos de tempo, conjuntos de relatórios ou caso de uso de análise. Os seguintes tipos de painel estão disponíveis no Analysis Workspace:

| Nome do painel | Descrição |
|---|---|
| [Painel em branco](blank-panel.md) | Escolha entre os painéis e visualizações disponíveis para start da análise. |
| [Painel do Quick Insights](quickinsight.md) | Crie rapidamente uma tabela de forma livre e uma visualização de acompanhamento para analisar e descobrir insights mais rapidamente. |
| [Painel do Analytics for Target](a4t-panel.md) | Analisar atividades e experiências do Target no Analysis Workspace. |
| [Painel de atribuição](attribution.md) | Compare rapidamente e visualize qualquer número de modelos de atribuição usando qualquer dimensão e métrica de conversão. |
| [Painel de forma livre](freeform-panel.md) | Realize comparações e detalhamentos ilimitados e, em seguida, adicione visualizações para contar uma história de dados avançada. |
| [Painel Visualizadores simultâneos de mídia](media-concurrent-viewers.md) | Analise os visualizadores simultâneos ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de analisar e comparar. |
| [Painel de comparação de segmentos](c-segment-comparison/segment-comparison.md) | Compare rapidamente dois segmentos em todos os pontos de dados para encontrar automaticamente diferenças relevantes. |

![](assets/panel-overview.png)

[!UICONTROL Os painéis Quick Insights], [!UICONTROL Em branco] e [!UICONTROL Forma livre] são excelentes locais para start de sua análise, enquanto o [!UICONTROL Analytics para Públicos alvos], [!UICONTROL Attribution IQ], Visualizadores   simultâneos de mídiae Comparação entre segmentos, se prestam a análises mais avançadas. Um botão `"+"` está disponível nos projetos para que você possa adicionar painéis em branco a qualquer momento.

The default starting panel is the [!UICONTROL Freeform] panel, but you can make the [blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md) your default as well.

## Conjunto de relatórios do painel {#report-suite}

Tabelas e visualizações em um painel derivam dados do conjunto [!UICONTROL de] relatórios selecionado na parte superior direita do painel. O conjunto de relatórios também determina quais componentes estão disponíveis no painel esquerdo. Em um projeto, você pode usar um ou [vários conjuntos](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) de relatórios, dependendo de seus casos de uso de análise.

![](assets/panel-report-suite.png)

## Calendário do painel {#calendar}

O calendário do painel controla o intervalo de relatórios para tabelas e visualizações em um painel.

Observação: Se um componente de intervalo de datas (roxo) for usado em uma tabela, visualização ou zona suspensa do painel, ele substituirá o calendário do painel.

![](assets/panel-calendar.png)

## Zona suspensa do painel {#dropzone}

A área suspensa do painel permite que você aplique filtros de segmento e lista suspensa a todas as tabelas e visualizações em um painel. Você pode aplicar um ou vários filtros a um painel. O título acima de cada filtro pode ser modificado clicando no lápis de edição ou você pode clicar com o botão direito do mouse para removê-lo completamente.

### Filtros de segmento

Arraste e solte qualquer segmento do painel esquerdo na área suspensa do painel para começar a filtrar o painel.

![](assets/segment-filter.png)

### Filtros de segmento Ad-hoc

Os componentes que não são de segmento também podem ser arrastados diretamente para a área de depósito para criar segmentos **** ad-hoc, economizando tempo e esforço de ir para o Construtor de segmentos. Segmentos criados dessa forma são definidos automaticamente como segmentos de nível de ocorrência. Essa definição pode ser modificada clicando no ícone de informações (i) ao lado do segmento, depois no ícone de edição em forma de lápis e editando-o no Construtor de segmentos.

Os segmentos ad-hoc são locais para o projeto e não serão exibidos no painel esquerdo, a menos que você os torne públicos.

![](assets/adhoc-segment-filter.png)

### Filtros suspensos {#dropdown-filter}

Além dos filtros de segmento, os filtros **** suspensos permitem interagir com os dados de forma controlada. Por exemplo, você pode adicionar um filtro suspenso para Tipos de dispositivo móvel para segmentar o painel por Tablet, Celular ou Desktop.

Filtros suspensos também podem ser usados para consolidar vários projetos em um único. Por exemplo, se você tiver muitas versões do mesmo projeto com diferentes segmentos de País aplicados, poderá consolidar todas as versões em um único projeto e adicionar um filtro suspenso de País.

![](assets/dropdown-filter-intro.png)

**Criar e usar filtros suspensos:**

![](assets/create-dropdown.png)

1. Para criar um filtro suspenso usando itens [!UICONTROL de]Dimension, como valores na dimensão [!UICONTROL do Canal] de marketing, clique no ícone de seta para a direita ao lado da dimensão no painel esquerdo. Isso exporá todos os itens disponíveis. Selecione um ou vários itens do componente no painel esquerdo e solte-os na área de depósito do painel **enquanto mantém pressionada a tecla** Shift. Isso transformará os componentes em um filtro suspenso, em vez de em um único segmento.
1. Para criar um filtro suspenso usando outro componente, como métricas, segmentos ou intervalos de datas, selecione de um tipo de componente no painel esquerdo e solte na área suspensa do painel **enquanto mantém pressionada a tecla** Shift.
1. Selecione uma das opções na lista suspensa para alterar os dados no painel. Também é possível optar por não filtrar os dados do painel ao selecionar **[!UICONTROL Nenhum filtro]**.

[Assista ao vídeo](https://www.youtube.com/watch?v=vpJywtsFVPI) para saber mais sobre como adicionar filtros suspensos ao seu projeto.
