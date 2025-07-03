---
description: Entenda o que são métricas e como usá-las no Analysis Workspace.
title: Métricas
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 21%

---

# Métricas

As métricas permitem quantificar os pontos de dados no Analysis Workspace. Elas são usadas com mais frequência como colunas em uma visualização e são vinculadas a dimensões.

## Utilização de métricas no Analysis Workspace

As métricas são flexíveis em seu uso no Analysis Workspace. Arraste uma métrica para uma Tabela de forma livre vazia para ver a tendência da métrica no período do projeto. Você também pode arrastar uma métrica quando uma dimensão estiver presente para ver como essa métrica se compara a cada item de dimensão. Arrastar uma métrica para cima de um cabeçalho de métrica existente a substitui e arrastar uma métrica ao lado de um cabeçalho permite ver ambas as métricas lado a lado.

Para obter informações sobre como adicionar métricas e outros tipos de componentes ao Analysis Workspace, consulte [Usar componentes no Analysis Workspace](use-components-in-workspace.md).

## Tipos de métricas

A Adobe oferece vários tipos de métricas para uso no Analysis Workspace:

* **Métricas padrão**: a maioria das métricas usadas em projetos é padrão. Os exemplos incluem [Visualizações de Página](/help/components/metrics/page-views.md), [Receita](/help/components/metrics/revenue.md)ou [Eventos personalizados](/help/components/metrics/custom-events.md). Consulte [Visão geral das métricas](/help/components/metrics/overview.md) no guia do usuário Componentes para obter mais informações.

* **Métricas calculadas** ![Calculadora](/help/assets/icons/Calculator.svg): métricas definidas pelo usuário baseadas em métricas padrão, números estáticos ou funções algorítmicas. As métricas calculadas definidas pelo usuário mostram um ícone de calculadora na lista de componentes disponíveis. Consulte [Visão geral das métricas calculadas](/help/components/c-calcmetrics/cm-overview.md) no guia do usuário Componentes para obter mais informações.

* **Modelos de métrica calculada** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg): métricas definidas pela Adobe que se comportam de forma semelhante às métricas calculadas. É possível usá-los como estão nos projetos do Workspace ou salvar uma cópia para personalizar sua lógica. Os modelos de métrica calculada mostram um ícone da Adobe na lista de componentes disponíveis.

Você pode ver se uma métrica foi aprovada ![ícone Aprovado](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) ou não. Para obter mais detalhes sobre uma métrica, passe o mouse sobre a métrica e selecione ![Ícone de informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Consulte [Informações do componente](use-components-in-workspace.md#component-info) para obter mais informações.


## Utilização de métricas no Analysis Workspace

As métricas podem ser usadas de várias maneiras no Analysis Workspace. Para obter informações sobre como adicionar métricas e outros tipos de componentes ao Analysis Workspace, consulte [Usar componentes no Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Usar métricas](https://video.tv.adobe.com/v/40817?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

## Criar métricas calculadas

Métricas calculadas permitem ver como as métricas se relacionam entre si, usando operadores simples ou funções estatísticas.


Há várias maneiras de criar métricas calculadas. O método escolhido determina se a métrica calculada estará disponível na lista de componentes em todos os projetos ou somente no projeto em que foi criada.

### Criar métricas calculadas para todos os projetos

Você pode usar o [construtor de métrica calculada](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) para [criar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-workflow.md). Quando criadas dessa forma, as métricas calculadas ficam disponíveis na lista de componentes e podem ser usadas em projetos em toda a organização.


### Criar métricas calculadas para um único projeto

Você pode criar rapidamente uma métrica calculada que esteja disponível somente para o projeto em que foi criada.

Para criar uma métrica calculada para um único projeto:

1. No Analysis Workspace, abra o projeto em que deseja criar a métrica calculada.

1. Em uma tabela de forma livre, clique com o botão direito do mouse no cabeçalho da coluna de uma única coluna.

   Ou

   Selecione duas colunas enquanto mantém pressionada a tecla Shift e clique com o botão direito do mouse em uma das colunas selecionadas.

1. Selecione **[!UICONTROL Criar métrica a partir da seleção]**

   ![Destaque do painel do Workspace Criar a partir da seleção](assets/create-metric-from-selection.png)

1. Para criar uma métrica calculada somente para este projeto, escolha entre as opções disponíveis.

   Quando uma única coluna é selecionada, as seguintes opções estão disponíveis:

   * [!UICONTROL **Média**]: cria uma nova coluna que mostra o valor médio no conjunto de elementos de dimensão para a coluna. Os valores da coluna usam a função [Média](/help/components/c-calcmetrics/cm-reference/cm-functions.md#mean).

   * [!UICONTROL **Mediana**]: cria uma nova coluna que mostra o valor mediano no conjunto de elementos de dimensão para a coluna. Os valores da coluna usam a função [Mediana](/help/components/c-calcmetrics/cm-reference/cm-functions.md#median).

   * [!UICONTROL **Coluna máx**]: cria uma nova coluna que mostra o maior valor no conjunto de elementos de dimensão para a coluna. Os valores da coluna usam a função [Máximo da Coluna](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-maximum).

   * [!UICONTROL **Coluna mín**]: cria uma nova coluna que mostra o menor valor no conjunto de elementos de dimensão para a coluna. Os valores da coluna usam a função [Mínimo da Coluna](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-minimum).

   * [!UICONTROL **Soma da coluna**]: cria uma nova coluna que adiciona todos os valores numéricos de uma métrica em uma coluna (entre os elementos de uma dimensão). Os valores da coluna usam a função [Soma da Coluna](/help/components/c-calcmetrics/cm-reference/cm-functions.md#column-sum).

   Quando duas colunas são selecionadas, as seguintes opções estão disponíveis:

   * [!UICONTROL **Dividir**]: cria uma nova coluna que divide os valores das duas colunas selecionadas.

   * [!UICONTROL **Subtrair**]: cria uma nova coluna que subtrai os valores das duas colunas selecionadas.

   * [!UICONTROL **Adicionar**]: cria uma nova coluna que adiciona os valores das duas colunas selecionadas.

   * [!UICONTROL **Multiplicar**]: cria uma nova coluna que multiplica os valores das duas colunas selecionadas.

   * [!UICONTROL **Alteração de porcentagem**]: cria uma nova coluna que mostra a alteração de porcentagem entre as duas colunas selecionadas.

[Métricas calculadas: métricas sem implementação](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics) (3:42)


## Comparar métricas com diferentes modelos de atribuição

Para comparar um modelo com outro rapidamente, clique com o botão direito em uma métrica e selecione **[!UICONTROL Comparar modelos de atribuição]**:

![Comparar atribuição](assets/compare-attribution.png)

Esse atalho permite comparar um modelo de atribuição a outro sem arrastar uma métrica e configurá-la duas vezes.

## Usar a função [!UICONTROL média cumulativa] para aplicar a suavização de métricas

Veja um vídeo sobre este tópico:


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Média cumulativa](https://video.tv.adobe.com/v/27068?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

