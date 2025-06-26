---
description: O Gerenciador de segmentos oferece várias formas de cuidar de segmentos, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.
title: Gerenciar segmentos (Gerenciador de segmentos)
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 16%

---

# Gerenciar segmentos


Você pode [compartilhar](t-seg-share.md), [segmentar](t-seg-filter.md), [marcar](seg-tag.md), [aprovar](seg-approve.md), renomear, [copiar](seg-copy.md), excluir, exportar segmentos e marcar segmentos como [favoritos](t-seg-favorite.md) de uma interface de gerenciamento de [!UICONTROL segmento] central. Para gerenciar segmentos:

* Selecione **[!UICONTROL Componentes]** na interface principal e, em seguida, **[!UICONTROL Segmentos]**.


>[!NOTE]
>
>Os segmentos rápidos criados em um projeto específico do Workspace não aparecem no gerenciador de [!UICONTROL Segmento], a menos que você tenha disponibilizado o segmento para todos os seus projetos.
>

## Gerenciador de segmentos

O Gerenciador de segmentos tem os seguintes elementos de interface:

![Interface de segmento](assets/segments-manager.png)

### Lista de segmentos

A lista de segmentos ➊ exibe todos os segmentos que você possui, os segmentos que foram segmentados para todos os seus projetos e os segmentos que foram compartilhados com você. A lista tem as seguintes colunas:

| Coluna | Descrição |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Selecione para favorecer ![Star](/help/assets/icons/Star.svg) ou desfavorecer ![StarOutline](/help/assets/icons/StarOutline.svg) um segmento. Ver [Marcar segmento como favorito](t-seg-favorite.md) |
| **[!UICONTROL Título e descrição]** | Para editar o segmento, selecione o link de título, que abre o [Construtor de segmentos](seg-build.md). Um segmento compartilhado é indicado com ![Compartilhamento](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Conjunto de relatórios]** | O conjunto de relatórios ao qual esse segmento se aplica. |
| **[!UICONTROL Proprietário]** | O proprietário do segmento. Como usuário, você só pode ver os segmentos que possui ou as anotações compartilhadas com você. |
| **[!UICONTROL Tags]** | As tags desse segmento. |
| **[!UICONTROL Compartilhado com]** | Com quantos indivíduos ou grupos você compartilhou o segmento. Selecione para abrir a caixa de diálogo **[!UICONTROL Compartilhar componente]**. Consulte [Compartilhar segmentos](t-seg-share.md) para obter mais informações. |
| **[!UICONTROL Publicado]** | Se o [segmento é publicado](seg-publish.md) no Experience Cloud. |
| **[!UICONTROL Data de modificação]** | A data e a hora em que o segmento foi modificado pela última vez. |

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar quais colunas deseja exibir.

### Barra de ação

Você pode executar ações em segmentos usando a barra de ações ➋. A barra de ação contém as seguintes ações:

| Ação | Descrição |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** | Adicione outro segmento, usando o [Construtor de segmentos](seg-build.md). |
| ![Search](/help/assets/icons/Search.svg) [!UICONTROL *Pesquisar por título*] | Quando nenhum segmento for selecionado na lista, pesquise por segmentos usando esse campo de pesquisa. |
| ![Rótulo](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Marcar os segmentos selecionados. Na caixa de diálogo **[!UICONTROL Segmento de Marca]**, selecione ou desmarque as marcas dos segmentos selecionados. Selecione **[!UICONTROL Salvar]** para salvar as marcas dos segmentos selecionados. Consulte [Marcar segmentos](seg-tag.md) para obter mais informações. |
| ![Compartilhar](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Compartilhar]** | Compartilhar os segmentos selecionados. Na caixa de diálogo **[!UICONTROL Compartilhar Segmento]**, você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar pessoas físicas ou grupos* ou selecionar **[!UICONTROL Organização]** ou **[!UICONTROL Grupos]**. Selecione **[!UICONTROL Salvar]** para salvar os detalhes de compartilhamento dos segmentos selecionados. Consulte [Compartilhar segmentos](t-seg-share.md) para obter mais informações. |
| ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** | Excluir os segmentos selecionados. Uma confirmação será solicitada. |
| ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Renomear]** | Renomeie um único segmento selecionado. Quando selecionada, você pode renomear o segmento em linha. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprovar]** | Aprove os segmentos selecionados. Consulte [Aprovar segmentos](seg-approve.md) para obter mais informações. |
| ![Copy](/help/assets/icons/Copy.svg)  **[!UICONTROL Copiar]** | Copie o segmento selecionado. Novos segmentos são criados com o mesmo nome e sufixo `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar para CSV]** | Exportar os segmentos para um arquivo `Segments List.csv`. |

### Barra de filtros ativos

A barra de filtros ➌ mostra os segmentos ativos aplicados do painel de filtros à lista de segmentos (se houver). É possível remover um filtro rapidamente usando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se mais de um filtro for especificado, você poderá remover todos os filtros usando **[!UICONTROL Remover tudo]**.

### Painel de filtro

Você pode filtrar a lista de segmentos usando o ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]** no painel esquerdo ➍. O painel de filtro exibe o tipo de filtro e o número de segmentos que respeitam o filtro específico. Selecione ![Filtro](/help/assets/icons/Filter.svg) para alternar a exibição do painel Filtro.

Consulte [Filtrar a lista de segmentos](t-seg-filter.md) para obter mais informações.


<!--

The Segment manager offers many ways of curating segments, such as sharing, filtering, tagging, approving, copying, deleting, and marking as favorites.

The Analytics Segment manager shows you all the segments you own and that have been shared with you. Admin-level users can see all segments in the organization. This overview presents the user interface and the capabilities of the Segment manager. 

![Segments manager](assets/segments-manager.png)

## Access the Segment manager

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**.

   Or 

   In an existing report, select the Segments icon ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) in the left navigation, then select **[!UICONTROL Manage]**.

## Available actions in the Segment manager

In the Segment manager, you can:

* [Filter segments](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Approve segments](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Tag segments](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Share segments](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Export a segment to a CSV file.

* [Copy segments](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Delete segments](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configure columns

You can configure the information displayed for each segment in the Segment manager by configuring the columns that are displayed.

To configure the visible columns in the Segment manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**. 

1. In the Segment manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Segment manager.

   The following columns are available:

   | Column title | Description  |
   |---|---|
   | Title and description | These values are provided in the Segment builder. To edit the title and description, select the title link to open the Segment builder.  |
   | Favorites  | Displays star icons next to each segment, allowing you to mark segments as favorites. For more information, see [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Report suites  | This column indicates in which report suite the segment was last saved.  |
   | Owner  | Indicates who owns the segment. As a non-Admin, you can see only segments you own or those that were shared with you.  |
   | Tags (not checked in column selector, hence column not appearing)  | Tags that were applied to the segment, either by you or by people who shared the segment with you.  |
   | Shared with  | Lists individuals or groups (Admin only) or All (Admin only) that you shared the segment with. <p>When a segment is being shared by you or with you, a share icon displays next to the segment name.</p>|
   | Date modified  | Shows the date that the segment was last modified.  |
   | Used in | Shows where segments are currently being used, and how many times they are being used in each area. <p>For example, if the segment is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**].</p> <p>Select the value in this column to see the breakdown of where the segments are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Alerts (2)**]). Furthermore, you can view the list of items where the segments are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of segments being used in that area:</p>  <ul><li>[!UICONTROL **Projects**]<p>Contains segments that were [created in the segment builder](/help/components/segmentation/segmentation-workflow/seg-build.md) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains segments that were [created as quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Alerts**]</li><li>[!UICONTROL **Calculated metrics**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a segment includes another segment in its definition, any use of that segment is not shown in the [!UICONTROL **Used in**] column. If a segment is included in the definition of another type of component (such as a calculated metric), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p>  |
   | Last used | Shows the date when the segment was last used in any of the following component types: <ul><li>Alerts</li><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li><li>Segments</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |
   
   {style="table-layout:auto"}

## How-To Video {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

This [Adobe Analytics video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html) gives a short overview of how to use the Segment manager.

-->