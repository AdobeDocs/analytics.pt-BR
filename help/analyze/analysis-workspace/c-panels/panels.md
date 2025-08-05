---
description: Entenda os painéis e como usá-los no Analysis Workspace.
title: Visão geral dos painéis
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: 19c2c1abd7f1799598597c0e696d0b001c1ef0ea
workflow-type: ht
source-wordcount: '2166'
ht-degree: 100%

---

# Visão geral dos painéis

Um [!UICONTROL painel] é uma coleção de tabelas e visualizações. Você pode acessar os painéis utilizando o ícone no canto superior esquerdo do espaço de trabalho ou por meio de um [painel em branco](/help/analyze/analysis-workspace/c-panels/blank-panel.md). Os painéis são úteis para organizar projetos de acordo com períodos, conjuntos de relatórios ou caso de uso de análise.

## Tipos de painel

Os seguintes tipos de painel estão disponíveis no Analysis Workspace para o [!UICONTROL Adobe Analytics]:

| Nome do painel | Descrição |
| --- | --- |
| [Painel em branco](/help/analyze/analysis-workspace/c-panels/blank-panel.md) | Escolha entre os painéis e visualizações disponíveis para iniciar a análise. |
| [Atribuição](attribution.md) | Compare e visualize modelos de atribuição rapidamente usando qualquer dimensão e métrica de conversão. |
| [Analytics for Target](a4t-panel.md) | Analisar atividades e experiências do Target no Analysis Workspace. |
| [Forma livre](freeform-panel.md) | Realize comparações e detalhamentos ilimitados e, em seguida, adicione visualizações para obter uma visão ampla dos dados. |
| [Público médio a cada minuto de mídia](average-minute-audience-panel.md) | Analise o público médio por minuto de um conteúdo específico ou ao longo de um período personalizado. |
| [Visualizadores simultâneos de mídia](media-concurrent-viewers.md) | Analise os visualizadores simultâneos ao longo do tempo, com detalhes sobre o pico de simultaneidade e a capacidade de criar um detalhamento e comparar. |
| [Tempo gasto com a reprodução da mídia](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) | Analise o tempo de reprodução gasto para entender onde ocorrem os picos de simultaneidade ou as desistências. |
| [Próximo item ou anterior](next-previous.md) | Mostra as páginas seguintes ou anteriores que as pessoas acessam. |
| [Insights rápidos](quickinsight.md) | Crie rapidamente uma tabela de forma livre e uma visualização de acompanhamento para analisar e descobrir insights mais rapidamente. |
| [Resumo da página](page-summary.md) | Explore as principais estatísticas sobre páginas específicas. |
| [Comparação de segmentos](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) | Compare rapidamente dois segmentos em todos os pontos de dados para encontrar automaticamente diferenças relevantes. |


Os painéis [!UICONTROL Insights rápidos], [!UICONTROL Em branco] e [!UICONTROL Forma livre] são ótimos lugares para começar a análise, enquanto que o painel [!UICONTROL Atribuição] é recomendado para análises mais avançadas. Um ![AddCircle](/help/assets/icons/AddCircle.svg) está disponível na parte inferior da tela para que você possa adicionar painéis em branco a qualquer momento.

O painel inicial padrão é o de [!UICONTROL Forma livre], mas você também pode definir o [Painel em branco](/help/analyze/analysis-workspace/c-panels/blank-panel.md) ou [Insights rápidos](/help/analyze/analysis-workspace/c-panels/quickinsight.md) como padrão. Consulte [Preferências de projetos e análise](/help/analyze/analysis-workspace/user-preferences.md#projects--analyses-preferences).


## Criar um painel

Para criar um painel:

* Arraste e solte um painel do menu esquerdo **[!UICONTROL Painéis]** sobre a tela.
* Selecione um painel no [Painel em branco](blank-panel.md).
* Use o menu **[!UICONTROL Inserir]** no espaço de trabalho e selecione seu painel. Você também pode usar qualquer um dos [atalhos](../build-workspace-project/fa-shortcut-keys.md) para inserir um painel.

  ![Criar um painel](assets/create-panel.png)

É possível:

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **em** qualquer painel para adicionar outra visualização. Isso exibe um pop-up que permite selecionar uma visualização.

  ![Pop-up mostrando possíveis visualizações](assets/blank-panel.png)

  | Selecione. | Para criar um(a)... |
  |---|---|
  | ![Tabela](/help/assets/icons/Table.svg) | [Tabela de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![Linha](/help/assets/icons/GraphTrend.svg) | [Linha](/help/analyze/analysis-workspace/visualizations/line.md) |
  | ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barra](/help//analyze/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Texto](/help/assets/icons/Text.svg) | [Texto](/help/analyze/analysis-workspace/visualizations/text.md) |
  | ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [Fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![Fluxo de trabalho](/help/assets/icons/GraphPathing.svg) | [Fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![GraphAreaStacked](/help/assets/icons/GraphAreaStacked.svg) | [Área empilhada](/help/analyze/analysis-workspace/visualizations/area.md) |
  | ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Tabela de coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![GraphBullet](/help/assets/icons/GraphBullet.svg) | [Marcador](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) |
  | ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Rosca](/help/analyze/analysis-workspace/visualizations/donut.md) |
  | ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Alteração de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Histograma](/help/assets/icons/Histogram.svg) | [Histograma](/help/analyze/analysis-workspace/visualizations/histogram.md) |
  | ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Dispersão](/help/analyze/analysis-workspace/visualizations/scatterplot.md) |
  | ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) |
  | ![GraphTree](/help/assets/icons/GraphTree.svg) | [Mapas de árvore](/help/analyze/analysis-workspace/visualizations/treemap.md) |

* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **fora** do último painel no espaço de trabalho para adicionar outro [painel em branco](blank-panel.md).


## Conjunto de relatórios

Cada painel é associado a um [conjunto de relatórios](/help/admin/admin/c-manage-report-suites/report-suites-admin.md), identificado pelo nome ![Dados](/help/assets/icons/Data.svg) **[!UICONTROL *do conjunto de relatórios *]**no menu suspenso, localizado no canto superior direito do painel.

Ao criar um novo painel, o conjunto de relatórios padrão se baseia no conjunto de relatórios do painel que você utilizou pela última vez no projeto do Analysis Workspace.

Em um projeto, é possível usar um ou [vários conjuntos de relatórios](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=pt-BR), dependendo dos casos de uso de análise. 

A lista dos conjuntos de relatórios é classificada de acordo com a relevância, a qual a Adobe define levando em conta quão recentemente e frequentemente o pacote foi usado pelo usuário atual e com que frequência o pacote é usado na organização.

![](assets/panel-report-suite.png)

>[!IMPORTANT]
>
>O conjunto de relatórios selecionado determina quais dimensões, métricas e segmentos estão disponíveis para criar visualizações em um painel.
>
>
>Ao alterar um conjunto de relatórios de um painel, alguns dos componentes podem não estar disponíveis no novo conjunto de relatórios. Essa alteração pode fazer com que a visualização não seja renderizada corretamente. Você poderá ver avisos como:
>
>* Esse painel contém componentes que não estão habilitados no conjunto de relatórios selecionado. Altere o conjunto de relatórios ou habilite os componentes necessários no conjunto de relatórios.
>* Não é possível renderizar a visualização: verifique as colunas e linhas para garantir que elas contenham componentes válidos.
>

## Calendário

O calendário do painel controla o intervalo de datas de relatórios para tabelas e visualizações em um painel.

>[!NOTE]
>
>Se um componente de intervalo de datas ![Calendário](/help/assets/icons/Calendar.svg) for usado em uma visualização ou painel (por exemplo, como um segmento), esse componente substituirá o calendário do painel.
>


![A janela do calendário mostrando o intervalo de datas selecionado.](assets/panel-calendar.png)

1. Selecione um intervalo de datas escolhendo primeiro a data inicial e, em seguida, a data final.
Também é possível selecionar uma **[!UICONTROL predefinição]** no menu suspenso [!UICONTROL *Selecionar uma predefinição*].

1. Ou selecione **[!UICONTROL Mostrar configurações avançadas]** para:

   * Especificar uma **[!UICONTROL Hora de início]** e **[!UICONTROL Hora de término]** diferentes das opções padrão `12:00 AM` (`0:00`) e `11:59 PM` (`23:59`). Os horários de término sempre incluem 59 segundos. No caso de um intervalo de datas que abrange muitos dias, a hora inicial se aplica ao primeiro dia do intervalo de datas, e a hora final se aplica ao último dia do intervalo de datas. Use **[!UICONTROL (Redefinir valores de tempo)]** para redefinir os valores padrão de hora inicial e final.
   * **[!UICONTROL Tornar os componentes do intervalo de datas relativos ao calendário do painel]**. Se essa opção estiver desabilitada, os componentes de intervalo de datas usados no painel serão relativos à hora atual. Se habilitada, os componentes de intervalo de datas usados no painel serão relativos ao calendário do painel.
   * **[!UICONTROL Usar datas contínuas]**. Se habilitada, os intervalos de datas predefinidos como **[!UICONTROL Últimos 7 dias completos]** são atualizados dinamicamente de acordo com a data e hora atuais. Se desabilitada, essas predefinições não são atualizadas depois de aplicadas.

     ![Datas contínuas](assets/calendar-rolling.png)

     É possível selecionar o texto entre parênteses (por exemplo, **[!UICONTROL início fixo - acumulado diário]**) para estender o painel e especificar detalhes para **[!UICONTROL Início]** e **[!UICONTROL Fim]**.

      1. Selecione **[!UICONTROL Início de]**, **[!UICONTROL Fim de]** ou **[!UICONTROL Dia fixo]**.
      1. Ao selecionar **[!UICONTROL Início de]** ou **[!UICONTROL Fim de]**, você pode criar uma expressão completa. Por exemplo: **[!UICONTROL Fim do]** **[!UICONTROL ano atual]** **[!UICONTROL mais]** `1` **[!UICONTROL dia]**. Escolha o valor apropriado para cada parte individual da expressão.
         * Selecione um valor para o atual. Por exemplo, **[!UICONTROL ano atual]**.
         * Selecione um valor para o cálculo adicional. Por exemplo, **[!UICONTROL mais]**.
         * Ao definir um cálculo adicional, especifique um valor. Por exemplo, `1`.
         * Depois de especificar o cálculo adicional, selecione o período a ser usado para o cálculo. Por exemplo, **[!UICONTROL dia]**.

     Selecione **[!UICONTROL Ocultar detalhes]** para ocultar os detalhes do cálculo de datas contínuas.

1. Selecione **[!UICONTROL Aplicar]** para aplicar o intervalo de datas ao painel no qual você abriu o calendário.
Selecione **[!UICONTROL Aplicar a todos os painéis]** para aplicar o intervalo de datas a todos os painéis no projeto do espaço de trabalho.


## Área de arrastar e soltar {#dropzone}

A área de destino do painel permite aplicar segmentos e segmentos suspensos a todas as tabelas e visualizações em um painel. É possível aplicar um ou mais segmentos a um painel.

### Segmentos

Arraste e solte os segmentos do painel à esquerda na área de destino do painel para começar a segmentá-lo. Repita esse processo para adicionar mais segmentos ao painel. Os segmentos aparecem lado a lado na parte superior do painel.

![O painel esquerdo mostra as métricas disponíveis e a métrica Cliente de dispositivo móvel arrastada para a área de destino do painel.](assets/segment-filter.png)

#### Segmentos rápidos

Além dos segmentos, também é possível arrastar outros tipos de componentes diretamente para a zona de destino para criar segmentos rápidos, economizando o tempo e esforço de usar o [Construtor de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md). Segmentos criados dessa forma são definidos automaticamente como segmentos em nível de evento. Para modificar rapidamente essa definição, selecione ![Editar](/help/assets/icons/Edit.svg) ao lado do nome do segmento.

<!-- For more information, see [Quick segments](/help/components/segmentation/). -->

![Segmentos ad hoc que são tornados públicos e soltos na área de destino.](assets/adhoc-segment-filter.png)

### Segmentos suspensos


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentos suspensos](https://video.tv.adobe.com/v/23877?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


#### Segmentos suspensos estáticos

Os segmentos suspensos estáticos permitem interagir com os dados de forma controlada. Por exemplo, é possível adicionar um segmento suspenso para Tipos de dispositivo móvel para segmentar o painel por Tablet, Celular ou Desktop.

Segmentos suspensos estáticos também podem ser usados para consolidar vários projetos em um único. Por exemplo, se você tiver muitas versões do mesmo projeto com diferentes segmentos de País aplicados, é possível consolidar todas as versões em um único projeto e adicionar um segmento suspenso de País.

![Os segmentos suspensos estáticos e o filtro “Direto” do canal de mercado destacado.](assets/dropdown-filter-intro.png)

##### Criar segmentos suspensos estáticos

* Para segmentos suspensos que usam itens de dimensão, selecione uma única dimensão no painel esquerdo e solte-a na área de destino do painel enquanto mantém pressionada a tecla ⇧ (*Shift*). Essa ação cria um segmento suspenso com todos os itens de dimensão que estão associados a essa dimensão.

  Ou, se quiser que o segmento suspenso inclua apenas itens de dimensão específicos associados a uma dimensão, clique no ícone de seta para a direita ao lado da dimensão desejada no painel esquerdo. Essa ação expõe todos os itens de dimensão disponíveis. Selecione vários itens de dimensão desta lista usando ⇧+![Selecionar](/help/assets/icons/Select.svg) (*shift* + *selecionar*) ou ^+![Selecionar](/help/assets/icons/Select.svg) (*control* + *selecionar*), depois solte-os na área de destino do painel **enquanto mantém pressionada a tecla** ⇧. 

* Para segmentos suspensos que usam um único tipo de componente (por exemplo, somente dimensões, somente segmentos ou somente métricas), selecione vários itens do mesmo tipo no painel esquerdo usando ⇧+![Selecionar](/help/assets/icons/Select.svg) ou ^+![Selecionar](/help/assets/icons/Select.svg). Em seguida, solte os itens na área de destino do painel **enquanto mantém pressionada a tecla** ⇧.

  Um único segmento suspenso será criado com os componentes selecionados.

* Para segmentos suspensos que usam uma mistura de tipos de componentes (como 2 métricas e 3 segmentos), selecione vários componentes usando ⇧+![Selecionar](/help/assets/icons/Select.svg) ou ^+![Selecionar](/help/assets/icons/Select.svg). Solte a seleção na área de destino do painel **enquanto mantém pressionada a tecla** ⇧. Nesse contexto, todos os tipos de componentes são tratados como segmentos suspensos separados. Por exemplo, se você incluir métricas e itens de dimensão na seleção, dois segmentos suspensos separados serão criados: um segmento suspenso que inclui itens de dimensão e outro que inclui métricas.

Um segmento suspenso fornece as seguintes opções no menu de contexto:

* **[!UICONTROL Excluir item suspenso]**: remove o segmento suspenso do painel.
* **[!UICONTROL Excluir rótulo]**: remove o texto exibido acima de um segmento suspenso. Para modificar o rótulo, passe o mouse sobre ele e selecione ![Editar rótulo do segmento suspenso](/help/assets/icons/Edit.svg).
* **[!UICONTROL Adicionar rótulo]**: ao adicionar um segmento suspenso a um projeto, um rótulo é definido automaticamente para o nome do componente. Se você excluir o rótulo, poderá adicioná-lo novamente com essa opção.
* **[!UICONTROL Exigir seleção]**: torna obrigatória a definição de um segmento no painel.

##### Usar segmentos suspensos estáticos

É possível usar o menu suspenso de segmento de qualquer uma das seguintes maneiras para segmentar o painel:

* Aplicar um único segmento ao painel selecionando o segmento na lista de segmentos suspensos.

* Aplicar vários segmentos ao painel selecionando mais de um segmento na lista de segmentos suspensos. O painel é segmentado para incluir qualquer um dos segmentos selecionados.


#### Segmentos suspensos dinâmicos

Os segmentos suspensos dinâmicos permitem determinar os valores disponíveis com base nos dados dentro do intervalo de relatórios do painel e nos valores de outros segmentos suspensos. Por exemplo, você pode criar dois menus suspensos dinâmicos usando uma dimensão Países e uma dimensão Cidades. Ao selecionar um país na lista suspensa **[!UICONTROL Países]**, a lista suspensa **[!UICONTROL Cidades]** se ajusta dinamicamente para mostrar apenas cidades desse país.

Esse mesmo conceito se aplica a todas as dimensões: somente os itens de dimensão que aparecem dentro do intervalo de datas do painel e dos segmentos selecionados são visíveis. Os itens de dimensão selecionados em segmentos suspensos estáticos afetam os valores disponíveis nos segmentos suspensos dinâmicos. No entanto, o inverso não é verdadeiro: os itens de dimensão selecionados em segmentos suspensos dinâmicos não afetam os valores disponíveis nos segmentos suspensos estáticos.

A seleção manual de itens de dimensão estará disponível se você antecipar que um determinado item de dimensão será coletado no futuro. Também é possível limpar um segmento suspenso dinâmico para que ele não contenha um valor, permitindo que outros segmentos suspensos dinâmicos contenham mais valores. Selecione **[!UICONTROL Redefinir tudo]** para limpar a seleção de todos os segmentos suspensos desse painel.

Para criar um segmento suspenso dinâmico:

* Arraste e solte uma única dimensão na área de destino do painel **enquanto mantém pressionada a tecla** ⇧.

Observe que os segmentos suspensos dinâmicos não estão disponíveis para métricas, segmentos ou intervalos de datas.

Um segmento suspenso dinâmico fornece as mesmas opções de menu de contexto que os segmentos suspensos estáticos.


## Menu de contexto

Outras funcionalidades do painel estão disponíveis por meio do menu de contexto (clique com o botão direito) no cabeçalho do painel.

![As opções disponibilizadas ao clicar com o botão direito em um cabeçalho de painel.](assets/right-click-menu.png)

As seguintes opções estão disponíveis:

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Inserir painel copiado]** | Permite colar um painel copiado em outro lugar dentro do projeto ou em um projeto diferente. |
| **[!UICONTROL Inserir visualização copiada]** | Cola uma visualização copiada em outro lugar dentro do painel, projeto ou em um projeto diferente. |
| **[!UICONTROL Aplicar o conjunto de relatórios a todos os painéis]** | Aplica o conjunto de relatórios desse painel a todos os outros painéis no projeto. |
| **[!UICONTROL Copiar painel]** | Copia um painel para que você possa inseri-lo em outro lugar dentro do projeto ou em um projeto diferente. |
| **[!UICONTROL Duplicar o painel]** | Cria uma duplicata exata do painel atual, a qual você pode modificar. |
| **[!UICONTROL Recolher todos os painéis]** | Recolhe todos os painéis do projeto. |
| **[!UICONTROL Expandir todos os painéis]** | Expande todos os painéis do projeto. |
| **[!UICONTROL Recolher todas as visualizações no painel]** | Recolhe todas as visualizações no painel atual. |
| **[!UICONTROL Expandir todas as visualizações no painel]** | Expande todas as visualizações no painel atual. |
| **[!UICONTROL Editar descrição]** | Adicione (ou edite) uma descrição de texto para o painel. |
| **[!UICONTROL Obter link do painel]** | Direciona alguém para um painel específico dentro de um projeto. Ao clicar no link, o destinatário deverá fazer logon antes de acessar o painel exato vinculado. |

## Configuração

Alguns painéis (como [!UICONTROL Atribuição], [!UICONTROL Experimentação], [!UICONTROL Público médio por minuto de mídia] e outros) têm uma caixa de diálogo de configuração para ajudar você a criar a visualização. Use a opção ![Editar](/help/assets/icons/Edit.svg) na parte superior do painel para acessar e alterar a configuração.

![Configurar um painel](/help/analyze/analysis-workspace/c-panels/assets/configure-panel.png)

<!--
## Panel types

The following panel types are available in Analysis Workspace:

| Panel name | Description |
| --- | --- |
| [Blank panel](blank-panel.md) | Choose from available panels and visualizations to start your analysis. |
| [Quick Insights panel](quickinsight.md) | Quickly build a freeform table and an accompanying visualization in order to analyze and uncover insights faster. |
| [Analytics for Target panel](a4t-panel.md) | Analyze Target activities and experiences in Analysis Workspace. |
| [Attribution panel](attribution.md) | Quickly compare and visualize any number of attribution models using any dimension and conversion metric. |
| [Freeform panel](freeform-panel.md) | Perform unlimited comparisons and breakdowns, then add visualizations to tell a rich data story. |
| [Media Average Minute Audience panel](average-minute-audience-panel.md) | Analyze average minute audience over time, with details on peak views and the ability to break down and compare. |
| [Media Concurrent Viewers panel](media-concurrent-viewers.md) | Analyze concurrent viewers over time, with details on peak concurrency and the ability to break down and compare. |
| [Media Playback Timespent panel](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) | Analyze concurrent viewers over time, with details on peak concurrency and the ability to break down and compare. |
| [Segment Comparison panel](c-segment-comparison/segment-comparison.md) | Quickly compare two segments across all data points to automatically find relevant differences. |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights], [!UICONTROL Blank] and [!UICONTROL Freeform] panels are great places to start your analysis, while [!UICONTROL Analytics for Target], [!UICONTROL Attribution], [!UICONTROL Media Concurrent Viewers] and [!UICONTROL Segment Comparison] lend themselves to more advanced analyses. A `"+"` button is available in projects so you can add blank panels at any time.

The default starting panel is the [!UICONTROL Freeform] panel, but you can make the [blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md) your default as well.

## Report suite {#report-suite}

Tables and visualizations within a panel derive data from the [!UICONTROL report suite] selected in the top right of the panel. The report suite also determines what components are available in the left rail. Within a project, you can use one or [many report suites](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=pt-BR) depending on your analysis use cases. To apply a single report suite to all panels in a project, **right-click panel header > Apply report suite to all panels**.

The list of report suites is sorted on relevancy, which Adobe defines based on how recently and frequently the suite has been used by the current user, and how frequently the suite is used within the organization.

![](assets/panel-report-suite.png)

## Calendar {#calendar}

The panel calendar controls the reporting range for tables and visualizations within a panel.

>[!NOTE]
>If a (purple) date range component is used within a table, visualization or panel drop zone, it overrides the panel calendar.

![](assets/panel-calendar.png)

You can apply a minute-level date range under the advanced settings of your panel calendar. If you are reporting on a date range that spans many days, start time applies to the first day and end time applies to the last day in your range.

## Drop zone {#dropzone}

The panel drop zone enables you to apply segment and drop-down filters to all tables and visualizations within a panel. You can apply one or many filters to a panel. 

### Segment filters

Drag and drop any segments from the left rail into the panel drop zone to begin filtering your panel. Repeat this process to add additional filters to the panel. Filters appear side by side at the top of the panel.

![Filter](assets/segment-filter.png)

### Ad hoc segment filters

Non-segment components can also be dragged directly into the drop zone to create ad hoc segments, saving you the time and effort of going to the Segment Builder. Segments created in this way are automatically defined as hit-level segments. This definition can be modified by clicking the information icon (i) next to the segment, then the pencil-shaped edit icon and editing it in the Segment Builder.

Ad hoc segments are a type of quick segment, and are local to the project. They do not show up in the left rail unless you make them public.

For more information, see [Quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### Static drop-down segments

Static drop-down segments enable you to interact with the data in a controlled way. For example, you can add a drop-down segment for Mobile Device Types so that you can segment the panel by Tablet, Mobile Phone, or Desktop.

Static drop-down segments can also be used to consolidate many projects into one. For example, if you have many versions of the same project with different Country segments applied, you can consolidate all versions into a single project and add a Country drop-down segment.

![](assets/dropdown-filter-intro.png)

#### Create static drop-down segments

* For drop-down segments using dimension items, select a single dimension from the left rail and drop it into the panel dropzone **while holding `[Shift]`**. This creates a drop-down segment with all the dimension items that are associated with that dimension. 

  Or, if you want the drop-down segment to include only specific dimension items that are associated with a dimension, click the right arrow icon next to the desired dimension in the left rail. This action exposes all available dimension items. Select multiple dimension items from this list using `[Shift + Click]` or `[Ctrl + Click]`, then drop them into the panel dropzone **while holding** `[Shift]`.

* For drop-down segments using a single component type (for example, only dimensions, or only segments, or only metrics), select multiple items of the same type in the left rail using `[Shift + Click]` or `[Ctrl + Click]`, then drop them into the panel dropzone **while holding `[Shift]`**.

  A single drop-down segment is created with components that you selected.

* For drop-down segments using a mix of component types (such as 2 metrics and 3 filters), select multiple components using `[Shift + Click]` or `[Ctrl + Click]`. Drop the selection into the panel dropzone **while holding `[Shift]`**. In this context, all component types are treated as separate drop-down segments. For example, if you include both metrics and dimension items in your selection, two separate drop-down segments are created: one drop-down segments includes dimension items, and the other includes metrics.

  ![The Panel window with the Mobile Customer segment field available to drop a static drop-down segment. ](assets/create-dropdown.png)

Right-clicking a drop-down segment provides the following options:

* **[!UICONTROL Delete drop-down]**: Removes the drop-down segment from the panel. 
* **[!UICONTROL Delete label]**: Remove the text above a drop-down segment. To modify the label, select the pencil icon.
* **[!UICONTROL Add label]**: When you add a drop-down segment to a project, a label is automatically set to the component name. If you delete the label, you can add it again with this option.
* **[!UICONTROL Require selection]**: Requires that a segment is set on the panel. 

[Watch the video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=pt-BR) to learn more about how to add drop-down filters to your project.

#### Use static drop-down segments

Use the drop-down segments menu in any of the following ways in order to filter the panel:
     
* Apply a single segment to the panel by selecting the segment from the drop-down menu.

* Apply multiple segments to the panel by selecting more than one segment from the drop-down menu. The panel is filtered to include any of the selected segments. 

  To remove a segment from the list, select it again in the drop-down menu.

  ![Select multiple segments](assets/dropdown-filter-multiselect.png)

### Dynamic drop-down segments

Dynamic drop-down segments allow you to determine available values based on data within the panel's reporting range and values in other drop-down segments. For example, you can create two dynamic drop-downs using the [Countries](/help/components/dimensions/countries.md) dimension and [Cities](/help/components/dimensions/cities.md) dimension. When you select a country from the [!UICONTROL Countries] drop-down list, the [!UICONTROL Cities] drop-down list dynamically adjusts to only show cities within that country.

This same concept applies to all dimensions; only dimension items that appear within the panel's date range and selected segments are visible. Dimension items selected in static drop-down segments affect available values in dynamic drop-down segments. However, the inverse is not true; Dimension items selected in dynamic drop-down segments do not affect available values in static drop-down segments.

Manual selection of dimension items is available if you anticipate a certain dimension item to be collected in the future. You can also clear a dynamic drop-down segment so that it does not contain a value, allowing other dynamic drop-down segments to contain more values. Select **[!UICONTROL Reset all]** to clear the selection from all drop-down segments for that panel.

To create a dynamic drop-down segment:

* Drag and drop a single dimension into the panel dropzone **while holding `[Shift]`**.
* Dynamic drop-down segments are not available for metrics, segments, or date ranges.
* Right-click a drop-down segment and select **[!UICONTROL Delete dropdown]** to delete it.

Right-clicking a dynamic drop-down filter provides the same options as static drop-down filters.

## Right-click menu {#right-click}

Additional functionality for a panel is available by right-clicking on the panel header.

![Right-click menu](assets/right-click-menu.png)

The following settings are available:

| Setting | Description |
| --- | --- |
| Insert Copied Panel/Visualization|Lets you paste ("insert") a copied panel or visualization to another place within the project, or into a different project.|
| Copy Panel | Lets you right-click and copy a panel, so that you can insert it to another place within the project, or into a different project.|
| Apply Report Suite to all panels | Lets you apply the active panel report suite to all panels in the project.|
| Duplicate Panel | Makes an exact duplicate of the current panel, which you can then modify. |
| Collapse/Expand all Panels | Collapses and expands all project panels. |
| Collapse/Expand all Visualizations in Panel | Collapses and expands all visualizations in the current panel. |
| Edit Description | Add (or edit) a text description for the panel. |
| Get Panel Link | Lets you direct someone to a specific panel within a project. When the link is clicked, the recipient will be required to login before being directed to the exact panel linked to. |

-->
