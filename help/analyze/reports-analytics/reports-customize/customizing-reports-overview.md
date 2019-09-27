---
description: Após executar um relatório, você pode personalizá-lo para visualizar e analisar os dados de acordo com suas necessidades. Você pode filtrar dados do relatório, alterar como os dados são apresentados graficamente, alterar a granularidade, etc.
seo-description: Após executar um relatório, você pode personalizá-lo para visualizar e analisar os dados de acordo com suas necessidades. Você pode filtrar dados do relatório, alterar como os dados são apresentados graficamente, alterar a granularidade, etc.
seo-title: Visão geral de Personalizar relatórios
solution: Analytics
title: Visão geral de Personalizar relatórios
topic: Reports and Analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

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
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Create Custom Report]**.
1. Dê um nome ao relatório e, em seguida, clique em **[!UICONTROL Salvar.]**

   Certifique-se de que você não tenha duplicado o nome de um relatório existente.

>[!MORE_LIKE_THIS]
>
>* [Personalização do menu](https://marketing.adobe.com/resources/help/en_US/reference/customize_menus.html)


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
   * Clique em **[!UICONTROL Selecionar predefinido]para selecionar uma data predefinida.**
   * Comparar datas.

1. Click **[!UICONTROL Run Report]**.

## Comparar datas {#task_95155C3700774B709F5FB81AE96B0824}

Etapas que descrevem como usar o calendário para executar comparações de datas entre relatórios classificados.

<!-- 

t_reports_comparing_dates.xml

 -->

Não é possível comparar datas entre relatórios de tendências.

>[!NOTE]
>
>If you want to perform a date comparison on key metrics in a dashboard, you can pull the data into [Report Builder](https://marketing.adobe.com/resources/help/en_US/arb/) using two separate requests. Em seguida, você pode usar fórmulas personalizadas no Excel para analisar a diferença entre os dois.

Para comparar datas entre relatórios classificados em Reports &amp; Analytics:

1. Executar um relatório.
1. Clique no calendário, no canto superior direito.
1. Click **[!UICONTROL Compare Dates]**.
1. Selecione as datas que deseja utilizar.
1. Click **[!UICONTROL Run Report]**.

## Exibir uma porcentagem como gráfico {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Etapas que descrevem como especificar a exibição do percentual em uma tabela de relatório como um gráfico.

<!-- 

t_reports_graph_percent.xml

 -->

A visualização também está disponível nos reportlets do painel.

1. Execute um relatório que tenha suporte a porcentagens como, por exemplo, o [!UICONTROL Relatório de páginas].
1. Click **[!UICONTROL Percent Shown As: Graph]**.

## Normalizar dados do relatório {#task_8005B55E59BD479DA67BC618FF8BC94A}

Etapas que descrevem como normalizar dados do relatório.

<!-- 

t_reports_normalize.xml

 -->

Após executar um relatório com as datas comparadas, ou comparações A/B, você pode normalizar os dados para exibir a porcentagem de alterações entre os relatórios. O conjunto de dados secundário é ajustado para compensar diferenças no número de dias selecionados, ou para diferentes volumes de tráfego.

**Para normalizar os dados de relatório**

1. Execute um relatório que suporta comparações de data.
1. Click **[!UICONTROL Compare Dates]**, then specify your date comparison.
1. Click **[!UICONTROL Run Report]**.
1. Click **[!UICONTROL Normalize Data: Yes]**.

## Selecionar um página para um relatório {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Etapas que descrevem como selecionar uma página específica nas páginas do seu site para um relatório.

<!-- 

t_reports_select_page.xml

 -->

1. Generate a report, such as a [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** &gt; **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Page Views]**).
1. Clique no link **Página selecionada.**
1. Em [!UICONTROL Selecionar página], selecione as páginas que deseja exibir.
1. Localize a página.
1. Click **[!UICONTROL OK.]**

## Comparar conjuntos de relatórios {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Etapas que descrevem como exibir relatório a partir de dois conjuntos de relatórios no mesmo relatório.

<!-- 

t_reports_compare_suites.xml

 -->

Além da exibição gráfica, a tabela do relatório fornece uma comparação em termos percentuais. Os relatórios a seguir podem ser executados com as comparações:

* Conteúdo do site
* Mobile
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
1.   Clique no link **Comparar com Site**. 
1. Localize o conjunto de relatórios.
1. Click **[!UICONTROL OK.]**

## Especificar a granularidade do relatório {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Etapas que descrevem como exibir totais de relatório com base horária, diária, semanal, mensal, trimestral ou anual.

<!-- 

t_reports_granularity.xml

 -->

O período de tempo do relatório determina quais opções de granularidade estão disponíveis. Por exemplo, você somente pode selecionar **[!UICONTROL Por hora]se tiver um período de um ou mais dias selecionado.** Você somente pode selecionar a granularidade **[!UICONTROL Anualmente]se tiver mais do que um ano selecionado.**

**Para especificar a granularidade de um relatório**

1. Generate a trended report, such as **[!UICONTROL Site Content]** &gt; **[!UICONTROL Pages.]**
1. Clique no link **Exibir por** e, em seguida, clique em granularidade.

## Executar um relatório de dia da semana {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Etapas que descrevem como executar relatórios em um dia específico da semana como, por exemplo, a cada segunda-feira em um intervalo de datas específico.

<!-- 

t_reports_day_of_week.xml

 -->

Este recurso aplica-se somente a relatórios de tendências filtrados com um intervalo de datas Por semana ou Por dia.

1. Execute um relatório de tendência em um intervalo de datas especificado.
1. Clique no link **Dias da semana** e, em seguida, clique no dia.

## Botão “Testar na Workspace”{#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Se você clicar no botão **[!UICONTROL Testar na Workspace]na parte superior de um relatório, isso carregará o mesmo relatório na Analysis Workspace.**

<!-- 

try_in_workspace.xml

 -->

A maioria dos relatórios no Reports &amp; Analytics inclui um botão “Testar na Workspace” para permitir que você reproduza a exibição atual na Analysis Workspace para obter personalização adicional.

No momento, o botão estará disponível somente se o nome do usuário tiver plenos direitos na Analysis Workspace.

Para obter mais informações sobre como personalizar seu relatório, consulte o guia da [Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/).
