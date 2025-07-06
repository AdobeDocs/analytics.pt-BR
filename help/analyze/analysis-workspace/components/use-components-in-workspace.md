---
description: Saiba como usar componentes em um projeto no Analysis Workspace
title: Usar Componentes Em Um Projeto
feature: Workspace Basics
role: User, Admin
exl-id: fb56e794-67e3-4f85-960e-b90684300fa0
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 80%

---

# Usar componentes em um projeto

Os componentes representam os dados reais de qualquer projeto no Analysis Workspace. Os componentes consistem em dimensões, métricas, segmentos e intervalos de datas. Você pode adicionar componentes a um projeto arrastando-os para visualizações ou painéis.

Consulte a [Visão geral dos componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) para obter mais informações sobre os tipos de componentes que você pode adicionar.

>[!TIP]
>
>Para obter informações sobre cada componente, use ![InfoOutline](/help/assets/icons/InfoOutline.svg). Consulte [Informações do componente](#component-info) para obter mais informações

## Adicionar componentes a um projeto

1. [Crie um projeto no Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

1. [Adicione um painel](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel) ou [uma visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) ao projeto no Analysis Workspace. Se você adicionar um componente a um projeto em branco, uma visualização de tabela de forma livre será criada.

1. Selecione ![Preparar](/help/assets/icons/Curate.svg) **[!UICONTROL Componentes]** no painel de botões. Você verá todos os componentes disponíveis no painel esquerdo. Consulte [Interface](/help/analyze/analysis-workspace/home.md#interface) para obter mais detalhes.

1. Role a tela até encontrar ou pesquise o componente que deseja adicionar e arraste-o até um painel ou visualização dentro do projeto.

1. Opcionalmente, é possível arrastar um componente para a zona de destino de segmentos no cabeçalho de um painel. Ao usar o recurso de arrastar e soltar, o componente é definido como um segmento e aplicado a todo o conteúdo dentro do painel.
Para obter informações sobre como você pode usar a área de destino do segmento em um painel para segmentar o seu painel, consulte a [Área de destino](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) na [Visão geral dos painéis](/help/analyze/analysis-workspace/c-panels/panels.md).

1. Para obter mais informações, consulte as seguintes seções:

   * [Adicionar dimensões a um projeto](#add-dimensions-to-a-project)

   * [Adicionar métricas a um projeto](#add-metrics-to-a-project)

   * [Adicionar segmentos a um projeto](#add-segments-to-a-project)

   * [Adicionar intervalos de datas a um projeto](#add-date-ranges-to-a-project)

### Adicionar dimensões a um projeto

[Dimensões](/help/components/dimensions/overview.md) são variáveis no Adobe Analytics que normalmente contêm valores de cadeia de caracteres. Por outro lado, as [métricas](/help/components/c-calcmetrics/cm-overview.md) contêm valores numéricos que se vinculam a uma dimensão. Um relatório básico mostra linhas de valores da sequência de caracteres (dimensão) em relação a uma coluna de valores numéricos (métrica).

1. Comece adicionando uma dimensão ao seu projeto no Analysis Workspace, conforme descrito em [Adicionar componentes a um projeto](#add-components-to-a-project).

1. Escolha um dos métodos a seguir para adicionar dimensões e determinar o tipo de dados que deseja analisar:

   ![Adicionar uma dimensão](assets/add-dimension.gif)

   * Arraste uma dimensão para uma visualização (como uma tabela de forma livre) no Analysis Workspace.

   * Arraste uma ou mais dimensões do painel esquerdo para a zona de destino de segmentos para criar um segmento rápido, conforme descrito em [Adicionar segmentos a um projeto](#add-filters-to-a-project).

1. Opcionalmente, é possível detalhar dimensões e itens de dimensão no Analysis Workspace com outros componentes. Para obter mais informações, consulte [Analisar dimensões no Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md).

Para obter mais informações sobre como usar dimensões no Analysis Workspace, consulte [Visualizar dimensões](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md), [Detalhar dimensões](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) e [Dimensões com separação de tempo](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md).

### Adicionar métricas a um projeto

As métricas permitem quantificar os pontos de dados no Analysis Workspace. Elas são usadas com mais frequência como colunas em uma visualização e são vinculadas a dimensões.

Para adicionar uma métrica a um projeto no Analysis Workspace:

1. Comece a adicionar uma métrica ao seu projeto no Analysis Workspace, conforme descrito em [Adicionar componentes a um projeto](#add-components-to-a-project).



1. Escolha um dos seguintes métodos para adicionar uma métrica no Analysis Workspace:

   ![Adicionar uma métrica](assets/add-metric.gif)

   * Arraste uma métrica para a zona de destino de métricas em uma tabela de forma livre vazia para ver a tendência dessa métrica ao longo do período do projeto.

   * Arraste uma métrica quando houver uma dimensão presente para analisar essa métrica em cada item de dimensão.

   * Arrastar uma métrica sobre um cabeçalho de métrica existente para substituí-lo.

   * Arraste uma métrica para o lado esquerdo ou direito de um cabeçalho de métrica existente para adicionar a nova métrica.

   * Arraste uma métrica acima ou abaixo de um cabeçalho de métrica existente para criar uma sobreposição de métrica.


Para obter mais informações sobre métricas, consulte [Métricas](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

### Adicionar segmentos a um projeto

[Segmentos](/help/components/segmentation/seg-overview.md) permitem identificar subconjuntos de pessoas, sessões ou eventos com base em características ou interações específicas.

Você pode usar segmentos no Analysis Workspace de qualquer uma das seguintes maneiras:

* Adicionar segmentos a um painel
Ao adicionar segmentos a um painel, os segmentos se aplicam a todo o conteúdo do painel.
Para obter informações sobre como você pode usar a área de destino do segmento em um painel para segmentar o seu painel, consulte a [Área de destino](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) na [Visão geral dos painéis](/help/analyze/analysis-workspace/c-panels/panels.md).

* Adicionar segmentos a uma visualização
Ao adicionar segmentos a uma coluna em uma tabela de forma livre, os segmentos se aplicam a todo o conteúdo na coluna da tabela. Você também pode adicionar segmentos como parte de uma visualização de fallout.

* Usar segmentos em componentes
Ao definir componentes como [métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md), [anotações](/help/analyze/analysis-workspace/components/annotations/create-annotations.md#annotation-builder) ou até mesmo [segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md), você pode usar segmentos como parte da definição.


### Adicionar intervalos de datas a um projeto

[Intervalos de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) determinam o período de relatório no Analysis Workspace. E um intervalo de dados pode ser aplicado a painéis em um projeto e também a algumas visualizações (como a Tabela de forma livre).

Cada painel inclui um intervalo de datas por padrão. Há várias maneiras de atualizar um intervalo de datas para um painel. Uma maneira de atualizar um intervalo de datas para um painel no Analysis Workspace é arrastar um componente de intervalo de datas do painel esquerdo:

1. Opcionalmente, é possível adicionar um intervalo de datas ao seu projeto no Analysis Workspace, conforme descrito em [Adicionar componentes a um projeto](#add-components-to-a-project).

1. Arraste e solte um intervalo de datas no painel esquerdo em:

   * Intervalo de datas atual, para modificar o intervalo de datas do painel.

     ![Soltar um intervalo de datas](assets/add-date-range.gif)

   * Uma métrica ou dimensão em uma visualização de tabela de forma livre. Consulte [Usar intervalos de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#use-date-ranges) para obter mais informações.

Para obter mais informações sobre como usar e gerenciar intervalos de datas no Analysis Workspace, consulte [Visão geral sobre intervalos de datas](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).

## Informações de componentes

Passe o mouse sobre qualquer componente para exibir ![Mais informações](/help/assets/icons/InfoOutline.svg). Quando você seleciona ![InfoOutline](/help/assets/icons/InfoOutline.svg), um pop-up é exibido com informações adicionais sobre o componente.

![Informações de componentes](assets/component-info.png)

Com base no seu controle de acesso, você pode:

* Acessar a definição do ![Marcador](/help/assets/icons/Bookmark.svg) [!UICONTROL Dicionário de dados] do componente.
* Acesse o construtor de componentes ![Editar](/help/assets/icons/Edit.svg) onde o componente está definido.




<!--
# Use components in Analysis Workspace

Components make up the actual data of any project in Analysis Workspace. Components consist of dimensions, metrics, segments, and date ranges. You can add components to a project by dragging them into visualizations or panels.

For overview information about the types of components you can add, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).

>[!TIP]
>
>For information about each component, select the Info icon next to a component's name in the left rail of Analysis Workspace, or see the [Analytics Components Guide](/help/components/home.md).

## Begin adding components to a project

1. [Create a project in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) if you haven't already.

1. [Add a panel](/help/analyze/analysis-workspace/c-panels/panels.md) or [add a visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) to the project in Analysis Workspace. 

   If you add a component to a blank project, a freeform table visualization is automatically created.

1. Select the **[!UICONTROL Components]** icon in the left rail.

   ![](assets/build-components.png)

1. Scroll to or search for the component you want to add, then drag it to a panel or visualization within your project. 

1. (Optional) Drag a component to the segment drop zone in a panel header. 

   Segments apply to all content within the panel.

   For information about how you can use the segment drop zone on a panel to filter your panel, see [Drop zone](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) in [Panels overview](/help/analyze/analysis-workspace/c-panels/panels.md).

   ![drop a segment in the drop zone](assets/segment-dropzone.png)

1. For more detailed information, continue with one of the following sections, depending on the component type you are adding:

   * [Add dimensions to a project](#add-dimensions-to-a-project)

   * [Add metrics to a project](#add-metrics-to-a-project)

   * [Add segments to a project](#add-segments-to-a-project)

   * [Add date ranges to a project](#add-date-ranges-to-a-project)

## Add dimensions to a project

[Dimensions](/help/components/dimensions/overview.md) are variables in Adobe Analytics that typically contain string values. Common dimensions include [Page](/help/components/dimensions/page.md), [Referring domain](/help/components/dimensions/referring-domain.md), or an [eVar](/help/components/dimensions/evar.md). In contrast, [metrics](/help/components/metrics/overview.md) contain numeric values that tie to a dimension. A basic report shows rows of string values (dimension), against a column of numeric values (metric).

1. Start adding a dimension to your project in Analysis Workspace, as described in [Begin adding components to a project](#begin-adding-components-to-a-project).

1. Choose one of the following methods to add dimensions and determine the type of data you want to analyze:

   * Drag a dimension to a visualization (such as a freeform table) in Analysis Workspace.

     ![Add dimensions to a project](assets/add-dimensions.png)
   
   * Drag one or more dimensions from the left rail onto the segment drop zone to create an ad hoc segment, as described in [Add segments to a project](#add-segments-to-a-project).

     ![drop a segment in the drop zone](assets/segment-dropzone.png)

1. (Optional) You can break down dimensions and dimension items in Analysis Workspace with other components. 

   For more information, see [Break down dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md).

For more information about how to use dimensions in Analysis Workspace, see [Preview dimensions](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md), [Break down dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md), and [Time-parting dimensions](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md).

## Add metrics to a project

[Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md) allow you to quantify data points in Analysis Workspace. They are most commonly used as columns in a visualization and tied to dimensions.

To add a metric to a project in Analysis Workspace:

1. Start adding a metric to your project in Analysis Workspace, as described in [Begin adding components to a project](#begin-adding-components-to-a-project).

1. Choose one of the following methods to add a metric in Analysis Workspace:

   * Drag a metric to the metric drop zone in an empty Freeform table to see that metric trended over the project's date period. 

     ![Add a metric to a project](assets/add-metrics.png)

   * Drag a metric when a dimension is present to see that metric compared to each dimension item. 

   * Drag a metric on top of an existing metric header to replace it.

   * Drag a metric next to a header to see both metrics side-by-side.

For more information about how to use metrics in Analysis Workspace, see [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

## Add segments to a project

[Segments](/help/components/segmentation/seg-overview.md) allow you to identify subsets of visitors based on characteristics or specific interactions.

You can use segments in Analysis Workspace in any of the following ways:

### Add segments to a panel

When you add segments to a panel, the segments apply to all content within the panel.

For information about how you can use the segment drop zone on a panel to filter your panel, see [Drop zone](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) in [Panels overview](/help/analyze/analysis-workspace/c-panels/panels.md).

### Add segments to a column in a freeform table

When you add segments to a column in a freeform table, the segments apply to all content within the table column.

### Use segments when creating calculated metrics

In the Calculated metric builder, you can apply segments within your metric definition. 

For more information, see [Segmented metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md).

## Add date ranges to a project

[Date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) determine the reporting time frame in Analysis Workspace, and can be applied to one or more panels within a project.

Each panel includes a date range by default. There are multiple ways to update a date range for a panel. One way to update a date range for a panel in Analysis Workspace is to drag a date range component from the left rail:

1. Start adding a date range to your project in Analysis Workspace, as described in [Begin adding components to a project](#begin-adding-components-to-a-project).

1. Drag a date range from the left rail onto the current date range in the upper-right portion of the panel.

     ![drop a date range](assets/daterange-drop.png)

For more information about how to use calendars and date ranges in Analysis Workspace, see [Calendar and date ranges overview](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).

-->