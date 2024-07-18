---
description: Execute um relatório de Análise de contribuição em um projeto do Workspace.
title: Executar análise de contribuição
role: User, Admin
exl-id: 20d1ba8d-3e4e-4702-ae28-5eb6bf00847b
feature: Anomaly Detection
source-git-commit: ee4772913c8b702658646755a2a11598c8530236
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 100%

---

# Executar análise de contribuição

A [Análise de contribuição](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) é um processo intensivo de aprendizado de máquina projetado para descobrir os contribuintes para uma anomalia observada no Adobe Analytics. O objetivo é auxiliar a encontrar áreas de foco ou oportunidades para análises adicionais de maneira muito mais rápida do que seria possível de outra forma.

## Executar análise de contribuição {#run}

Há duas maneiras de invocar a análise de contribuição em um projeto:

* Em uma tabela de forma livre com granularidade diária, clique com o botão direito em qualquer linha e selecione **[!UICONTROL Executar análise de contribuição]**. Você também pode executá-la em linhas que não exibem nenhuma anomalia.

  >[!NOTE]
  >
  >Atualmente oferecemos suporte à análise de contribuição somente com granularidade diária.

  ![](assets/run_ca.png)

* Em um gráfico de linhas, passe o mouse sobre um dado de anomalia. Clique no link **[!UICONTROL Analisar]**.

  ![](assets/contribution-analysis.png)

1. (Opcional) Depois de clicar em **[!UICONTROL Executar análise de contribuição]** no gráfico de linhas ou em uma tabela, você pode limitar o escopo (e, portanto, acelerar) da análise, [excluindo dimensões](#exclude).

1. Aguarde o carregamento da análise de contribuição. Isso pode levar um tempo considerável, dependendo do tamanho do seu conjunto de relatórios e do número de dimensões. A análise de contribuição realiza análises nos 50.000 itens principais por dimensão.
1. O Analysis Workspace carrega um novo painel de Análise de contribuição diretamente neste projeto. 

   * Uma visualização que mostra o número de **Visitas** no dia.
   * Uma **linha de Tendência de visitas** mensal para contexto.
   * Os **Itens principais** que contribuíram para esta anomalia, classificados por [pontuação de contribuição](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis), mais a métrica em questão e uma métrica de visitante únicos para colocar a métrica no contexto de uma perspectiva de dimensionamento.

   * A tabela [Segmentos gerados](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=pt-BR) (Grupos de itens principais) identifica associações dos itens principais com base na Pontuação de contribuição, nas ocorrências de anomalias e no percentual geral que contribuiu para a métrica anômala. Isso é então capturado como um segmento de público-alvo (Segmento de contribuição 1, Segmento de contribuição 2, etc.). Clicar no botão “i” (informações) fornecerá uma exibição da definição de cada segmento automático, incluindo os itens principais que os constituem:

     ![](assets/auto_segment.png)

1. Como a análise de contribuição agora faz parte do Analysis Workspace, você pode aproveitar seus vários recursos a partir de um menu acessado clicando com o botão direito em uma tabela, tornando sua análise ainda mais significativa, como:

   * [Detalhar cada item de dimensão por outra dimensão.](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [Executar tendência de uma ou mais linhas.](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Adicionar novas visualizações.](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [Criar alertas.](/help/components/c-alerts/intellligent-alerts.md)
   * [Criar ou comparar segmentos.](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]
>
>Destacamos a anomalia que está sendo analisada com um ponto azul na Análise de contribuição e nos projetos de alertas inteligentes vinculados a ela. Essa ação oferece uma indicação mais clara da anomalia que está sendo analisada.

## Excluir dimensões da Análise de contribuição {#exclude}

Certas vezes, você pode querer excluir algumas dimensões da Análise de contribuição. Por exemplo, você pode não se preocupar sobre qualquer navegador ou dimensões relacionadas ao hardware, e deseja agilizar a análise os removendo.

1. Depois de clicar em **[!UICONTROL Executar Análise de contribuição]** (ou em **[!UICONTROL Analisar]** em um gráfico de linhas), o painel **[!UICONTROL Dimensões excluídas]** é exibido.

1. Arraste qualquer dimensão não desejada até o painel **[!UICONTROL Dimensões excluídas]** e salve a lista clicando em **[!UICONTROL Definir como padrão]**. Ou clique em **[!UICONTROL Limpar tudo]** para começar de novo a seleção de dimensões a serem excluídas.

   ![](assets/exclude_dimensions.png)

1. Depois de ter adicionado as dimensões a serem excluídas (ou não), clique novamente em **[!UICONTROL Executar análise de contribuição]**.
1. Caso precise revisar a lista de dimensões excluídas, clique duas vezes em Dimensões e a lista de dimensões excluídas é exibida:

   ![](assets/excluded-dimensions.png)

1. Exclua qualquer dimensão não desejada ao clicar no x próximo a ela. Em seguida, salve a lista ao clicar em **[!UICONTROL Definir como padrão]**.
