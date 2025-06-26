---
description: Execute um relatório de Análise de contribuição em um projeto do Workspace.
title: Executar análise de contribuição
role: User, Admin
exl-id: 20d1ba8d-3e4e-4702-ae28-5eb6bf00847b
feature: Anomaly Detection
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 15%

---

# Executar análise de contribuição

A [Análise de contribuição](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) é um processo intensivo de aprendizado de máquina projetado para descobrir os contribuintes para uma anomalia observada no Adobe Analytics. O objetivo é auxiliar a encontrar áreas de foco ou oportunidades para análises adicionais de maneira muito mais rápida do que seria possível de outra forma.

>[!NOTE]
>
>A Análise de contribuição é compatível somente com dados com granularidade diária.

As etapas para executar a Análise de contribuição são:

1. Invocar análise de contribuição em um projeto.

   ![Executar análise de contribuição](assets/run-contribution-analysis.png)

   1. Em uma visualização de Linha, com base em uma tabela de forma livre com granularidade diária, selecione um ponto de dados de anomalia. No pop-up, selecione **[!UICONTROL Analisar]**.
   1. Em uma tabela de forma livre com granularidade diária, no menu de contexto de qualquer linha, selecione **[!UICONTROL Executar análise de contribuição]**. Você pode até mesmo executar a análise em linhas que não exibem nenhuma anomalia.
   1. Em uma tabela de forma livre com granularidade diária, em uma linha que indica uma anomalia:
      1. Selecione o indicador ◥.
      1. Na caixa de diálogo ![Alerta](/help/assets/icons/Alert.svg) **[!UICONTROL Anomalia detectada]**, selecione **[!UICONTROL Abrir Análise de Contribuição]**.



1. (Opcional) Você pode limitar o escopo (e, portanto, acelerar) da análise por [excluindo dimensões](#exclude-dimensions).

   ![Excluindo dimensões da Análise de contribuição](assets/excluding-dimensions.png)

1. Selecione **[!UICONTROL Executar análise de contribuição]**.

1. Aguarde enquanto a análise de contribuição é processada. O processamento pode levar um tempo considerável, dependendo do tamanho do conjunto de relatórios e do número de dimensões. A análise de contribuição realiza a análise dos 50.000 itens principais por dimensão. Você também é notificado sobre o número de [tokens de análise de contribuição](anomaly-detection.md#contribution-analysis-tokens) restantes.

   ![Análise de contribuição em execução](assets/contribution-analysis-executing.png)

1. O Analysis Workspace carrega um novo painel **[!UICONTROL Análise de contribuição]** diretamente neste projeto.

   ![Painel de análise de contribuição](assets/contribution-analysis.png)

   * Uma visualização de [número de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md).
   * Uma visualização mensal de tendência [line](/help/analyze/analysis-workspace/visualizations/line.md).
   * Uma **[!UICONTROL Tabela de forma livre]** [de itens principais](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) que mostra quais itens principais contribuem para essa anomalia, classificados por [Pontuação de contribuição](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis). As colunas adicionais mostram a métrica em questão e uma métrica **[!UICONTROL Visitantes únicos]** para fornecer contexto.

   * A **[!UICONTROL Tabela de forma livre]** de [Segmentos gerados (clusters de itens principais)](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) identifica associações de itens principais com base na Pontuação de contribuição, nas ocorrências de anomalias e na porcentagem geral que contribui para a métrica anômala. Essa associação é capturada como um segmento de público-alvo (Segmento de contribuição 1, Segmento de contribuição 2, etc.). Selecione ![Informações](/help/assets/icons/Info.svg) para exibir a definição do segmento, incluindo os itens principais dos quais os segmentos são compostos:


1. Como a análise de contribuição agora faz parte do Analysis Workspace, você pode aproveitar vários de seus recursos em um menu de contexto de tabela de forma livre para tornar sua análise ainda mais significativa, como:

   * [Detalhar cada item de dimensão por outra dimensão](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [Executar tendência de uma ou mais linhas](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [Adicionar novas visualizações](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [Criar alertas](/help/components/c-alerts/intellligent-alerts.md)
   * [Crie ou compare segmentos.](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]
>
>A anomalia analisada é destacada com um ponto azul na Análise de contribuição e nos projetos de alertas inteligentes vinculados a ela. Esse destaque fornece uma indicação mais clara da anomalia que está sendo analisada.


## Excluir dimensões

Talvez você queira excluir algumas dimensões da Análise de contribuição. Por exemplo, você pode não se preocupar sobre qualquer navegador ou dimensões relacionadas ao hardware, e deseja agilizar a análise os removendo.

Para gerenciar a dimensão excluída:

* Arraste qualquer dimensão não desejada para o painel **[!UICONTROL Dimensões Excluídas]** e salve a lista clicando em **[!UICONTROL Definir como Padrão]**.

* Selecione **[!UICONTROL Limpar tudo]** para começar de novo.

* Selecione ![Dimensões](/help/assets/icons/Dimensions.svg) para exibir um menu de contexto e use ![CrossSize400](/help/assets/icons/CrossSize400.svg) para remover qualquer dimensão excluída selecionada da lista.

  ![](assets/excluded-dimensions-list.png)

Depois de modificar as dimensões a serem excluídas, selecione **[!UICONTROL Executar análise de contribuição]** novamente.

