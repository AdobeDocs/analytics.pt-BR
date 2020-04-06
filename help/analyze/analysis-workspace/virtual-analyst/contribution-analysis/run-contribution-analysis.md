---
description: 'null'
title: Executar análise de contribuição
uuid: 5282a5f9-0771-4974-93cb-335204bde114
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Executar análise de contribuição

A Análise de contribuição é um processo intensivo de aprendizado de máquina projetado para descobrir contribuidores para uma anomalia observada no Adobe Analytics. O objetivo é ajudar o usuário a encontrar áreas de foco ou oportunidades para análises adicionais muito mais rapidamente do que seria possível de outra forma.

## Executar análise de contribuição {#section_7D2C5E48A5664727941DF4C90976D9DC}

Há duas maneiras de invocar a análise de contribuição em um projeto:

* In a freeform table with daily granularity, right-click any row and select **[!UICONTROL Run Contribution Analysis]**. Você também pode executá-la em linhas que não exibem nenhuma anomalia.

   >[!NOTE]
   >
   >Atualmente oferecemos suporte à análise de contribuição somente com granularidade diária.

   ![](assets/run_ca.png)

* Em um gráfico de linhas, passe o mouse sobre um dado de anomalia. Click the **[!UICONTROL Analyze]** link that appears.

   ![](assets/contribution-analysis.png)

1. (Optional) After you have clicked **[!UICONTROL Run Contribution Analysis]** in either the line chart or a table, you can narrow the scope of (and thus speed up) the analysis by [excluding dimensions](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC).

1. Aguarde enquanto sua análise de contribuição é carregada. Isso pode levar um tempo considerável, dependendo do tamanho do conjunto de relatórios e do número de dimensões. A análise de contribuição executa análise nos 50.000 itens principais por dimensão.
1. O Analysis Workspace carrega um novo painel de Análise de contribuição diretamente neste projeto. Você observará vários painéis familiares se tiver usado a Análise de contribuição em Relatórios e análises antes:

   * Uma visualização que mostra o número de **Visitas** naquele dia.
   * Uma linha **de Tendência de** visitas mensal para contexto.
   * **Principais itens** que contribuíram para essa anomalia, classificados pela pontuação [de](https://marketing.adobe.com/resources/help/pt_BR/analytics/contribution/ca_contribution_score.html)contribuição, mais a métrica em questão e uma métrica de Visitantes únicos para contextualizar a métrica de uma perspectiva de dimensionamento.

   * A tabela Segmentos [](https://marketing.adobe.com/resources/help/pt_BR/analytics/contribution/ca_workflow_premium.html) gerados (Grupos de itens principais) identifica associações de itens principais com base na Pontuação de contribuição, nas ocorrências de anomalias e na porcentagem geral que contribui para a métrica anômala. Isso é capturado como um segmento de audiência (Segmento de contribuição 1, Segmento de contribuição 2 etc.). Clicar no botão &quot;i&quot; (informações) fornecerá uma visualização da definição de cada segmento automático, incluindo quais itens principais ele é composto:

      ![](assets/auto_segment.png)

1. Como a análise de contribuição agora faz parte do Analysis Workspace, você pode aproveitar seus vários recursos a partir de um menu acessado clicando com o botão direito em uma tabela, tornando sua análise ainda mais significativa, como:

   * [Detalhar cada item de dimensão por outra dimensão.](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [Executar tendência de uma ou mais linhas.](/help/analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Adicionar novas visualizações.](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [Criar alertas.](/help/components/c-alerts/intellligent-alerts.md)
   * [Criar ou comparar segmentos.](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE] Destacamos a anomalia que está sendo analisada com um ponto azul na Análise de contribuição e nos projetos de alertas inteligentes vinculados a ela. Essa ação oferece uma indicação mais clara da anomalia que está sendo analisada.

## Excluir dimensões da Análise de contribuição {#section_F6932F4BF74544B5872164E7B1E0C6FC}

Pode haver momentos em que você deseja excluir algumas dimensões da Análise de contribuição. Por exemplo, talvez você não se importe com qualquer navegador ou dimensões relacionadas a hardware, e deseja acelerar a análise removendo-as.

1. Depois de clicar **[!UICONTROL Run Contribution Analysis]** (ou **[!UICONTROL Analyze]** em um gráfico de linhas), o **[!UICONTROL Excluded Dimensions]** painel é exibido.

1. Arraste qualquer dimensão indesejada para o **[!UICONTROL Excluded Dimensions]** painel e salve a lista clicando em **[!UICONTROL Set as Default]**. Or, click **[!UICONTROL Clear All]** to start over with selecting dimensions to exclude.

   ![](assets/exclude_dimensions.png)

1. After you have added dimensions to exclude (or chosen not to), click **[!UICONTROL Run Contribution Analysis]** again.
1. Caso precise revisar a lista de dimensões excluídas, clique duas vezes em Dimensões e a lista de dimensões excluídas é exibida:

   ![](assets/excluded-dimensions.png)

1. Just delete any unwanted dimensions by clicking the x next to them, then save the list by clicking **[!UICONTROL Set as Default]**.

