---
description: Depois de executar um relatório, você pode personalizá-lo para visualização e analisar os dados de acordo com suas necessidades. Você pode filtrar dados de relatório, alterar a forma como os dados são apresentados graficamente, alterar a granularidade de datas e assim por diante.
title: Visão geral de Personalizar relatórios
topic: Reports and analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Visão geral de Personalizar relatórios

Depois de executar um relatório, você pode personalizá-lo para visualização e analisar os dados de acordo com suas necessidades. Você pode filtrar dados de relatório, alterar a forma como os dados são apresentados graficamente, alterar a granularidade de datas e assim por diante.

## Criar um relatório personalizado {#task_BA6EACA3039C40AEA5605E1D8C76E646}

Etapas que descrevem como salvar a configuração atual de um relatório como um novo relatório personalizado para todos os usuários visualizarem.

<!-- 

t_reports_custom.xml

 -->

Somente administradores podem criar um relatório personalizado. Quando você cria um relatório personalizado, ele é adicionado ao menu principal do relatórios ao lado do relatório no qual ele se baseia.

**Para criar um relatório personalizado**

1. Execute um relatório e configure-o conforme necessário.
1. Clique em **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Name the report, then click **[!UICONTROL Save.]**

   Certifique-se de que você não tenha duplicado o nome de um relatório existente.

>[!MORELIKETHIS]
>
>* [Personalização do menu](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/customize-menus.translate.html)


## Selecionar um intervalo de datas ou data {#task_9BEF7D4D839A4748B76E8500D1406C34}

Etapas que descrevem como usar escolhem os períodos de tempo para seus dados de relatório.

<!-- 

t_reports_select_date.xml

 -->

Você pode selecionar dias, semanas, meses ou anos específicos. Você também pode executar relatórios de comparação.

Ao abrir um painel com reportlets que têm intervalos de datas diferentes, você pode escolher um novo intervalo de datas no calendário. As alterações se aplicam a todos os reportlets no painel.

**Para selecionar um intervalo de datas**

1. Executar um relatório.
1. Clique no ícone do calendário, no canto superior direito.
1. Selecione uma data.

   É possível:

   * Visualização dias, meses ou períodos de ano (até três).
   * Arraste o cursor pelas datas para selecionar um intervalo.
   * Insira as datas manualmente.
   * Clique no nome de um mês para selecionar um mês.
   * Clique **[!UICONTROL Select Preset]** para selecionar uma data predefinida.
   * Comparar datas.

1. Clique em **[!UICONTROL Run Report]**.

## Comparar datas {#task_95155C3700774B709F5FB81AE96B0824}

Etapas que descrevem como você pode usar o calendário para executar comparações de datas entre relatórios classificados.

<!-- 

t_reports_comparing_dates.xml

 -->

Não é possível comparar datas entre relatórios de tendências.

>[!NOTE] Se você deseja executar uma comparação de datas sobre métricas principais em um painel, é possível puxar os dados no [Construtor de relatórios](https://marketing.adobe.com/resources/help/pt_BR/arb/) com duas solicitações separadas. Em seguida, você pode usar fórmulas personalizadas no Excel para analisar a diferença entre os dois.

Para comparar datas entre relatórios classificados em Relatórios e análises:

1. Executar um relatório.
1. Clique no calendário, no canto superior direito.
1. Clique em **[!UICONTROL Compare Dates]**.
1. Selecione as datas que deseja utilizar.
1. Clique em **[!UICONTROL Run Report]**.

## Exibir uma porcentagem como gráfico {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Etapas que descrevem como especificar se a porcentagem deve ser exibida em uma tabela de relatório como um gráfico.

<!-- 

t_reports_graph_percent.xml

 -->

Esta visualização também está disponível em reportlets de painel.

1. Run a report that supports percentages, such as a [!UICONTROL Pages Report].
1. Clique em **[!UICONTROL Percent Shown As: Graph]**.

## Normalizar dados do relatório {#task_8005B55E59BD479DA67BC618FF8BC94A}

Etapas que descrevem como normalizar os dados do relatório.

<!-- 

t_reports_normalize.xml

 -->

Depois de executar um relatório com datas comparadas ou para comparações A/B, você pode normalizar os dados para mostrar a porcentagem de alteração entre os relatórios. O conjunto de dados secundário é ajustado para compensar as diferenças no número de dias selecionados ou para diferentes volumes de tráfego.

**Para normalizar os dados do relatório**

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

Etapas que descrevem como exibir relatórios de dois conjuntos de relatórios no mesmo relatório.

<!-- 

t_reports_compare_suites.xml

 -->

Além da exibição gráfica, a tabela do relatório fornece uma comparação de porcentagem. Os seguintes relatórios podem ser executados com comparações:

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

Etapas que descrevem como visualização os totais do relatório de forma horária, diária, semanal, mensal, trimestral ou anual.

<!-- 

t_reports_granularity.xml

 -->

O período de tempo do relatório determina quais opções de granularidade estão disponíveis. Por exemplo, você pode selecionar somente **[!UICONTROL Hourly]** se tiver um período de um ou dois dias selecionado. Você pode selecionar somente **[!UICONTROL Yearly]** a granularidade se tiver mais de um ano selecionado.

**Especificação da granularidade do relatório**

1. Gerar um relatório de tendências, como **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Click the **[!UICONTROL View by]** link, then click a granularity.

## Executar um relatório de dia da semana {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Etapas que descrevem como executar relatórios em um dia específico da semana, como em cada segunda-feira em um intervalo de datas específico.

<!-- 

t_reports_day_of_week.xml

 -->

Esse recurso se aplica somente aos relatórios de tendências filtrados com um intervalo de datas de Semana ou Dia.

1. Execute um relatório de tendência em um intervalo de datas especificado.
1. Clique no **[!UICONTROL Day of Week]** link e, em seguida, clique em um dia.

## Botão “Testar na Workspace” {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Clicar no **[!UICONTROL Try In Workspace]** botão na parte superior de um relatório carregará o mesmo relatório na área de trabalho da Análise.

<!-- 

try_in_workspace.xml

 -->

A maioria dos relatórios no Relatórios e análises agora inclui um botão &quot;Tentar na Workspace&quot; para permitir que você reproduza a visualização atual na Análise Workspace para personalização adicional.

Atualmente, o botão só está disponível se o seu nome de usuário tiver direitos totais para a Área de trabalho de Análise.

Para obter mais informações sobre todas as maneiras de personalizar seu relatório, consulte o guia Área de trabalho da [Análise](https://marketing.adobe.com/resources/help/pt_BR/analytics/analysis-workspace/) .
