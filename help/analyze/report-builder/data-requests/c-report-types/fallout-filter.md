---
description: Descreve as etapas envolvidas na aplicação de filtros para um relatório de fallout.
seo-description: Descreve as etapas envolvidas na aplicação de filtros para um relatório de fallout.
seo-title: Filtrar um relatório de fallout usando o Assistente de solicitação
solution: Analytics
title: Filtrar um relatório de fallout usando o Assistente de solicitação
topic: Construtor de relatórios
uuid: 269 e 900 e -23 bd -48 d 8-9 bac -69 e 3167 a 9 c 18
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Filtrar um relatório de fallout usando o Assistente de solicitação

Descreve as etapas envolvidas na aplicação de filtros para um relatório de fallout.

Esse exemplo mostra o relatório Fallout de página.

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. Selecione o conjunto de relatórios apropriado.
1. In the tree view on the left, select **[!UICONTROL Paths]** &gt; **[!UICONTROL Page]** &gt; **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. Configure the appropriate [date ranges](../../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).
1. Click **[!UICONTROL Next]**.
1. In Step 2 of the Wizard, under **[!UICONTROL Row Labels]**, click the **[!UICONTROL Define Checkpoints]** link. (Em um relatório de fallout, é sempre necessário definir os elementos de caminho, diferente de um relatório de caminho, no qual o padrão é pré-aplicado). 

   ![](assets/define_checkpoints.png)

1. Select the **[!UICONTROL Filter]** option.

1. In the **[!UICONTROL Define Site Section Fallout Checkpoints]** dialog, define checkpoints from a range of cells or from a list. Em seguida, clique em **[!UICONTROL OK]**.
1. Decida se deseja selecionar a partir de várias células ou de uma lista.
1. If you select from a list, click **[!UICONTROL Add]** to select checkpoints to add to the fallout path. Você pode definir entre 3 e 8 pontos de verificação. (Pesquisa por elementos disponíveis ao clicar em **[!UICONTROL Mais]**.)

   For more information on refining the filter, see [Filter Dimensions](../../../../analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md#concept_9C0518E2CF604AADA97DDBB1B4ECAAF8). 1. Move **[!UICONTROL Available Elements]** from the left column to the right by selecting them and clicking the orange arrow.
1. Click **[!UICONTROL OK]** three times, then click **[!UICONTROL Finish]**.

   O relatório deve atualizar agora.