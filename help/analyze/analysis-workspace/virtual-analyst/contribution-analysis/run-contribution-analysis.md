---
description: 'null'
seo-description: 'null'
seo-title: Executar análise de contribuição
title: Executar análise de contribuição
uuid: 5282 a 5 f 9-0771-4974-93 cb -335204 bde 114
translation-type: tm+mt
source-git-commit: 8b2feced9fd503395d06dc12c8e5d7985ca89161

---


# Executar análise de contribuição

A Análise de contribuição é um processo intensivo de aprendizado de máquina projetado para descobrir contribuintes para uma anomalia observada no Adobe Analytics. O objetivo é auxiliar o usuário a encontrar áreas de foco ou oportunidades para análises adicionais de maneira muito mais rápida do que seria possível de outra forma.

## Executar a análise de contribuição {#section_7D2C5E48A5664727941DF4C90976D9DC}

Há duas maneiras de invocar a análise de contribuição em um projeto:

* Em uma tabela de forma livre com granularidade diária, clique com o botão direito em qualquer linha e selecione **[!UICONTROL Executar análise de contribuição]**. Você também pode executá-la em linhas que não exibem qualquer anomalia.

   >[!NOTE]
   >
   >Atualmente suportamos a análise de contribuição somente com granularidade diária.

   ![](assets/run_ca.png)

* Em um gráfico de linha, passe por cima de um ponto de dados de anomalia. Clique no link **[!UICONTROL Analisar]que aparecerá.**

   ![](assets/contribution-analysis.png)

1. (Opcional) Depois de clicar em **[!UICONTROL Executar análise de contribuição]** no gráfico de linha ou em uma tabela, você pode limitar o escopo (e, portanto, acelerar) da análise, [excluindo dimensões](../../../../analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC).

1. Aguarde o carregamento da análise de contribuição. Isso pode levar um tempo considerável, dependendo do tamanho do seu conjunto de relatórios e do número de dimensões. A análise de contribuição realiza análises nos 50.000 itens principais por dimensão.
1. A Analysis Workspace carrega um novo painel de Análise de contribuição diretamente neste projeto. Você observará vários painéis familiares se já tiver utilizado a Análise de contribuição nos Reports &amp; Analytics:

   * Uma visualização que mostra o número de **Visitas** no dia.
   * Uma **linha de Tendência de visitas** mensal para contexto.
   * Os **Itens principais** que contribuíram para esta anomalia, classificados por [pontuação de contribuição](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_contribution_score.html), mais a métrica em questão e uma métrica de Visitantes exclusivos para colocar a métrica no contexto de uma perspectiva de dimensionamento.

   * A tabela [Segmentos gerados](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_workflow_premium.html) (Grupos de itens principais) identifica associações dos itens principais com base na Pontuação de contribuição, nas ocorrências de anomalias e no percentual geral que contribuiu para a métrica anômala. Isso é então capturado como um segmento de público-alvo (Segmento de contribuição 1, Segmento de contribuição 2, etc.). Clicar no botão “i” (informações) fornecerá uma exibição da definição de cada segmento automático, incluindo os itens principais que os constituem:

      ![](assets/auto_segment.png)

1. Como a análise de contribuição agora faz parte da Analysis Workspace, você pode aproveitar seus vários recursos a partir de um menu acessado clicando com o botão direito em uma tabela, tornando sua análise ainda mais significativa, como:

   * [Detalhar cada item de dimensão por outra dimensão.](../../../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md#task_B594DA2476E84DFDA8279E831F0BD9C4)
   * [Executar tendência de uma ou mais linhas.](../../../../analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Adicionar novas visualizações.](../../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276)
   * [Criar alertas.](/help/components/c-alerts/intellligent-alerts.md)
   * [Criar ou comparar segmentos.](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md#concept_74FAC1C6D0204F9190A110B0D9005793)

>[!NOTE]
>
>Destacamos a anomalia que está sendo analisada com um ponto azul na Análise de contribuição e nos projetos de Alertas inteligentes vinculados a ela. Essa ação oferece uma indicação mais clara da anomalia que está sendo analisada.

## Exclude dimensions from Contribution Analysis {#section_F6932F4BF74544B5872164E7B1E0C6FC}

Certas vezes, você pode querer excluir algumas dimensões da Análise de contribuição. Por exemplo, você pode não se preocupar sobre qualquer navegador ou dimensões relacionadas ao hardware, e deseja agilizar a análise os removendo.

1. Depois de clicar em **[!UICONTROL Executar Análise de contribuição]** (ou **[!UICONTROL Alisar]em uma linha de gráfico), o painel** Dimensões excluídas] é exibido.**[!UICONTROL **

1. Arraste qualquer dimensão não desejada até o painel **[!UICONTROL Dimensões excluídas]** e salve a lista clicando em **[!UICONTROL Definir como padrão]**. Ou clique em **[!UICONTROL Limpar tudo]para começar de novo a seleção de dimensões a serem excluídas.**

   ![](assets/exclude_dimensions.png)

1. Depois de ter adicionado as dimensões para excluir (ou não), clique novamente em **[!UICONTROL Executar análise de contribuição].**
1. Caso precise revisar a lista de dimensões excluídas, clique duas vezes em Dimensões e a lista de dimensões excluídas é exibida:

   ![](assets/excluded-dimensions.png)

1. Exclua qualquer dimensão não desejada ao clicar no x próximo a ela; em seguida, salve a lista ao clicar em **[!UICONTROL Definir como padrão]**.

