---
description: Após executar um relatório, você pode personalizá-lo para visualizar e analisar os dados de acordo com suas necessidades. Você pode filtrar dados do relatório, alterar como os dados são apresentados graficamente, alterar a granularidade, etc.
title: Visão geral de Personalizar relatórios
topic: Reports and analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Visão geral de Personalizar relatórios

Após executar um relatório, você pode personalizá-lo para visualizar e analisar os dados de acordo com suas necessidades. Você pode filtrar dados do relatório, alterar como os dados são apresentados graficamente, alterar a granularidade, etc.

## Criar um relatório personalizado {#task_BA6EACA3039C40AEA5605E1D8C76E646}

Etapas que descrevem como salvar a configuração atual de um relatório como um novo relatório personalizado para que todos os usuários possam exibir.

<!-- 

t_reports_custom.xml

 -->

Somente administradores podem criar um relatório personalizado. Ao criar um relatório personalizado, ele é adicionado ao menu principal de relatórios, ao lado do relatório que serviu de base para o relatório personalizado.

**Para criar um relatório personalizado**

1. Execute um relatório e configure-o conforme necessário.
1. Clique em **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Name the report, then click **[!UICONTROL Save.]**

   Certifique-se de que você não tenha duplicado o nome de um relatório existente.

>[!MORELIKETHIS]
>
>* [Personalização do menu](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/customize-menus.html)


## Selecionar um intervalo de datas ou data {#task_9BEF7D4D839A4748B76E8500D1406C34}

Etapas que descrevem como escolher os períodos de tempo dos dados de relatório.

<!-- 

t_reports_select_date.xml

 -->

Você pode selecionar dias específicos, semanas, meses ou anos. Você também pode executar relatórios de comparação.

Quando você abre um painel com reportlets que têm intervalos de datas diferentes, você pode escolher um novo intervalo de datas no calendário. As alterações se aplicam a todos os reportlets no painel.

**Para selecionar um intervalo de datas**

1. Executar um relatório.
1. Clique no ícone do calendário, no canto superior direito.
1. Selecione uma data.

   É possível:

   * Visualizar dias, meses ou períodos do ano (até três).
   * Arrastar o cursor em datas para selecionar um intervalo.
   * Inserir datas manualmente.
   * Clicar em um nome de mês para selecionar um mês.
   * Clique **[!UICONTROL Select Preset]** para selecionar uma data predefinida.
   * Comparar datas.

1. Clique em **[!UICONTROL Run Report]**.

## Comparar datas {#task_95155C3700774B709F5FB81AE96B0824}

Etapas que descrevem como usar o calendário para executar comparações de datas entre relatórios classificados.

<!-- 

t_reports_comparing_dates.xml

 -->

Não é possível comparar datas entre relatórios de tendências.

>[!NOTE] Se você deseja executar uma comparação de datas sobre métricas principais em um painel, é possível puxar os dados no [Construtor de relatórios](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/report-builder/home.html) com duas solicitações separadas. Em seguida, você pode usar fórmulas personalizadas no Excel para analisar a diferença entre os dois.

Para comparar datas entre relatórios classificados em Reports &amp; Analytics:

1. Executar um relatório.
1. Clique no calendário, no canto superior direito.
1. Clique em **[!UICONTROL Compare Dates]**.
1. Selecione as datas que deseja utilizar.
1. Clique em **[!UICONTROL Run Report]**.

## Exibir uma porcentagem como gráfico {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Etapas que descrevem como especificar a exibição do percentual em uma tabela de relatório como um gráfico.

<!-- 

t_reports_graph_percent.xml

 -->

A visualização também está disponível nos reportlets do painel.

1. Run a report that supports percentages, such as a [!UICONTROL Pages Report].
1. Clique em **[!UICONTROL Percent Shown As: Graph]**.

## Normalizar dados do relatório {#task_8005B55E59BD479DA67BC618FF8BC94A}

Etapas que descrevem como normalizar dados do relatório.

<!-- 

t_reports_normalize.xml

 -->

Após executar um relatório com as datas comparadas, ou comparações A/B, você pode normalizar os dados para exibir a porcentagem de alterações entre os relatórios. O conjunto de dados secundário é ajustado para compensar diferenças no número de dias selecionados, ou para diferentes volumes de tráfego.

**Para normalizar os dados de relatório**

1. Execute um relatório que suporta comparações de data.
1. Clique em **[!UICONTROL Compare Dates]**, em seguida, especifique sua comparação de datas.
1. Clique em **[!UICONTROL Run Report]**.
1. Clique em **[!UICONTROL Normalize Data: Yes]**.

## Selecionar um página para um relatório {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Etapas que descrevem como selecionar uma página específica nas páginas do seu site para um relatório.

<!-- 

t_reports_select_page.xml

 -->

1. Gere um relatório, como um [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Page Views]**).
1. Click the **[!UICONTROL Selected Page]** link.
1. On [!UICONTROL Choose Page], select the pages you want to display.
1. Localize a página.
1. Clique em **[!UICONTROL OK.]**

## Comparar conjuntos de relatórios {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Etapas que descrevem como exibir relatório a partir de dois conjuntos de relatórios no mesmo relatório.

<!-- 

t_reports_compare_suites.xml

 -->

Além da exibição gráfica, a tabela do relatório fornece uma comparação em termos percentuais. Os relatórios a seguir podem ser executados com as comparações:

* Conteúdo do site
* Dispositivo móvel
* Fontes de Tráfego
* Campanhas
* Produtos
* Retenção de visitante
* Perfil do visitante
* Conversão personalizada
* Tráfego personalizado
* Target
* Survey

**Para comparar conjuntos de relatórios**

1. Crie um relatório que permite que você compare relatórios.
1. Click the **[!UICONTROL Compare to Site]** link.
1. Localize o conjunto de relatórios.
1. Clique em **[!UICONTROL OK.]**

## Especificar a granularidade do relatório {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Etapas que descrevem como exibir totais de relatório com base horária, diária, semanal, mensal, trimestral ou anual.

<!-- 

t_reports_granularity.xml

 -->

O período de tempo do relatório determina quais opções de granularidade estão disponíveis. For example, you can select only **[!UICONTROL Hourly]** if you have a one or two day time frame selected. You can select only **[!UICONTROL Yearly]** granularity if you have more than one year selected.

**Para especificar a granularidade de um relatório**

1. Gerar um relatório de tendências, como **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Click the **[!UICONTROL View by]** link, then click a granularity.

## Executar um relatório de dia da semana {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Etapas que descrevem como executar relatórios em um dia específico da semana como, por exemplo, a cada segunda-feira em um intervalo de datas específico.

<!-- 

t_reports_day_of_week.xml

 -->

Este recurso aplica-se somente a relatórios de tendências filtrados com um intervalo de datas Por semana ou Por dia.

1. Execute um relatório de tendência em um intervalo de datas especificado.
1. Clique no **[!UICONTROL Day of Week]** link e, em seguida, clique em um dia.

## Botão “Testar na Workspace” {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Clicking the **[!UICONTROL Try In Workspace]** button at the top of a report will load the same report in Analysis Workspace.

<!-- 

try_in_workspace.xml

 -->

A maioria dos relatórios no Reports &amp; Analytics inclui um botão “Testar na Workspace” para permitir que você reproduza a exibição atual na Analysis Workspace para obter personalização adicional.

No momento, o botão estará disponível somente se o nome do usuário tiver plenos direitos na Analysis Workspace.

Para obter mais informações sobre como personalizar seu relatório, consulte o guia da [Analysis Workspace](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/analysis-workspace-features.html).
