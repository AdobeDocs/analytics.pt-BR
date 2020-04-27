---
description: Descreve as etapas envolvidas na aplicação de filtros para um relatório de fallout.
title: Filtrar um relatório de fallout com o assistente de solicitação
topic: Report builder
uuid: 269e900e-23bd-48d8-9bac-69e3167a9c18
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtrar um relatório de fallout com o assistente de solicitação

Descreve as etapas envolvidas na aplicação de filtros para um relatório de fallout.

Esse exemplo mostra o relatório Fallout de página.

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. Selecione o conjunto de relatórios apropriado.
1. Na visualização em árvore à esquerda, selecione **[!UICONTROL Paths]** > **[!UICONTROL Page]** > **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. Configure os [intervalos de datas](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) apropriados.
1. Clique em **[!UICONTROL Next]**.
1. Na Etapa 2 do Assistente, em **[!UICONTROL Row Labels]**, clique no **[!UICONTROL Define Checkpoints]** link. (Em um relatório de fallout, é sempre necessário definir os elementos de caminho, diferente de um relatório de caminho, no qual o padrão é pré-aplicado).

   ![](assets/define_checkpoints.png)

1. Selecione a opção **[!UICONTROL Filter]**.

1. Na caixa de **[!UICONTROL Define Site Section Fallout Checkpoints]** diálogo, defina pontos de verificação a partir de várias células ou de uma lista. Em seguida, clique em **[!UICONTROL OK]**.
1. Decida se deseja selecionar a partir de várias células ou de uma lista.
1. If you select from a list, click **[!UICONTROL Add]** to select checkpoints to add to the fallout path. Você pode definir entre 3 e 8 pontos de verificação. (Search for available elements by clicking **[!UICONTROL More]**.)

   Para obter mais informações sobre como refina o filtro, consulte [Dimensões do filtro](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md). 1. Move **[!UICONTROL Available Elements]** from the left column to the right by selecting them and clicking the orange arrow.
1. Click **[!UICONTROL OK]** three times, then click **[!UICONTROL Finish]**.

   O relatório deve atualizar agora.
