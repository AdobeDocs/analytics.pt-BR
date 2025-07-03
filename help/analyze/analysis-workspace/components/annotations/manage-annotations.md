---
title: Gerenciar anotações
description: Saiba como gerenciar anotações no Analysis Workspace.
role: User, Admin
feature: Annotations
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 88%

---

# Gerenciar anotações

Você pode compartilhar, filtrar, marcar, aprovar, copiar, excluir anotações e adicioná-las aos favoritos utilizando a interface de gerenciamento central [!UICONTROL Anotações]. Para gerenciar anotações:

* Selecione **[!UICONTROL Componentes]** na interface principal e clique em **[!UICONTROL Anotações]**.


>[!NOTE]
>
>As anotações criadas em um projeto específico do espaço de trabalho não aparecem no gerenciador [!UICONTROL Anotações], a menos que você tenha disponibilizado ela para todos os seus projetos.
>

## Gerenciador de anotações

O Gerenciador de anotações tem os seguintes elementos de interface:

![Interface de anotações](assets/annotations-manager.png)

### Lista de anotações

A lista de anotações ➊ exibe todas as anotações que você possui, as anotações que foram segmentadas para todos os seus projetos e as anotações que foram compartilhadas com você. A lista tem as seguintes colunas:

| Coluna | Descrição |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Selecione ![Estrela](/help/assets/icons/Star.svg) para adicionar ou ![StarOutline](/help/assets/icons/StarOutline.svg) para remover uma anotação dos favoritos. |
| **[!UICONTROL Título e descrição]** | Fornecidos no Criador de anotações. Para editar o título e a descrição, clique no link de título para abrir o [Criador de anotações](/help/analyze/analysis-workspace/components/annotations/create-annotations.md#annotation-builder). Uma anotação compartilhada é indicada pelo ícone ![Compartilhamento](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Conjunto de relatórios]** | Os conjuntos de relatórios aos quais esta anotação se aplica. |
| **[!UICONTROL Proprietário]** | O(a) proprietário(a) da anotação. Como usuário, você só vê as anotações que possui ou as que são compartilhadas com você. |
| **[!UICONTROL Intervalo de datas aplicado]** | A data ou o intervalo de datas ao qual essa anotação se aplica. |
| **[!UICONTROL Tags]** | As tags dessa anotação. |
| **[!UICONTROL Compartilhado com]** | As pessoas ou grupos com os quais você compartilhou a anotação. Selecione para abrir a caixa de diálogo **[!UICONTROL Compartilhar componente]**. |
| **[!UICONTROL Data de modificação]** | Mostra a data e a hora em que a anotação foi modificada pela última vez. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar quais colunas deseja exibir.

### Barra de ação

É possível executar ações em anotações usando a barra de ações ➋. A barra de ação contém as seguintes ações:

| Ícone | Ação | Descrição |
|:--:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Adicionar]** | Adicione outra anotação usando o [Criador de anotações](create-annotations.md#annotation-builder). |
| ![Pesquisar](/help/assets/icons/Search.svg) | [!UICONTROL *Pesquisar por título*] | Se nenhuma anotação for selecionada na lista, pesquise por anotações usando esse campo de pesquisa. |
| ![Rótulo](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Marque as anotações selecionadas. Na caixa de diálogo **[!UICONTROL Componente de tag]**, marque ou desmarque as tags das anotações selecionadas. Clique em **[!UICONTROL Salvar]** para salvar as tags das anotações selecionadas. |
| ![Compartilhar](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Compartilhar]** | Compartilhe as anotações selecionadas. Na caixa de diálogo **[!UICONTROL Compartilhar componente]**, você pode ![Pesquisar](/help/assets/icons/Search.svg) *pesquisar indivíduos ou grupos* ou selecionar **[!UICONTROL Organização]** ou **[!UICONTROL Grupos]**. Clique em **[!UICONTROL Salvar]** para salvar os detalhes de compartilhamento das anotações selecionadas. Consulte [Compartilhar anotações](#share-annotations) para obter mais detalhes. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Exclui as anotações selecionadas. Será solicitada uma confirmação. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Renomear]** | Renomeia uma única anotação selecionada. Quando selecionada, você pode renomear a anotação em linha. |
| ![Copiar](/help/assets/icons/Copy.svg) | **[!UICONTROL Copiar]** | Copia as anotações selecionadas. Novas anotações são criadas com o mesmo nome e sufixo (Copiar) |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar para CSV]** | Exporta as anotações para um arquivo `Annotations List.csv`. |

### Barra de filtros ativos

A barra de filtros ➌ mostra os filtros ativos (se houver). É possível remover um filtro rapidamente usando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se mais de um filtro for especificado, você poderá remover todos os filtros usando **[!UICONTROL Remover tudo]**.

### Painel de filtro

Você pode filtrar anotações usando o **[!UICONTROL Filtro]** no painel esquerdo ➍. O painel de filtros exibe o tipo de filtro e o número de anotações que se enquadram no filtro. Selecione ![Filtro](/help/assets/icons/Filter.svg) para alternar a exibição do painel de filtros.

Para filtrar a lista de filtros:

1. Selecione ![Filtro](/help/assets/icons/Filter.svg) para abrir o painel Filtros. Se você precisar de mais espaço para a lista de filtros, selecione ![Filtro](/help/assets/icons/Filter.svg) mais uma vez para fechar o painel.
1. É possível filtrar as anotações usando qualquer uma das [seções de filtro](#filter-sections) disponíveis.

   >[!INFO]
   >
   >Os *itens* referem-se às anotações exibidas na [Lista de anotações](manage-annotations.md#annotations-list).
   > 

#### Seções de filtro

{{tagfiltersection}}
{{reportsuitefiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


A [Lista de anotações](manage-annotations.md#annotations-list) é atualizada automaticamente com base na sua configuração de filtro. É possível ver os filtros configurados na [Barra de filtros ativos](manage-annotations.md#active-filter-bar).


## Editar anotações

É possível editar uma anotação de duas formas:

* Em um projeto do espaço de trabalho, use o ícone [Informações do componente](/help/analyze/analysis-workspace/components/use-components-in-workspace.md#component-info).

* Na lista [[!UICONTROL Anotações]](#annotations-list), selecione o título da anotação.

Use o [Criador de anotações](/help/analyze/analysis-workspace/components/annotations/create-annotations.md#annotation-builder) para editar a anotação.

## Compartilhar anotações

O seguinte se aplica ao compartilhar anotações ou trabalhar com anotações que foram compartilhadas com você:

* As anotações somente de projeto pertencentes a um projeto que você compartilhou com outros usuários também aparecem para esses usuários. Os usuários não podem editar ou excluir essas anotações somente de projeto.
* Se você salvar uma anotação e compartilhá-la diretamente com um usuário, esse usuário poderá editar e excluir a anotação somente se tiver direitos de admin.

* As anotações criadas em um projeto que foi compartilhado com você aparecerão somente nesse projeto. Se a anotação for compartilhada diretamente com você, ela aparecerá em todos os projetos nos quais ela pode ser exibida.

## Anotações e fusos horários

Todas as anotações são criadas com um carimbo de data e hora, mas sem informações de hora ou fuso horário. No momento do relatório, é usado o fuso horário do conjunto de relatórios configurado para o painel.


<!--
# Manage annotations

The [!UICONTROL Annotations manager] shows you all of the annotations that you own or that have been shared with you. Project-specific annotations do not appear here. You can use this interface to share, filter, tag, copy, delete, and favorite your annotations. Administrators can manage and approve annotations.

**[!UICONTROL Components]** > **[!UICONTROL Annotations]**

## Annotations Manager user interface

![](assets/annotation-mgr.png)

| UI Element | Description |
| --- | --- | 
| [!UICONTROL Title and Description] | Provided in the Annotations Builder. To edit the title and description, click the title link - this takes you back to the Annotations Builder.  |
| [!UICONTROL Report Suite] | The report suites that this annotation applies to.  | 
| [!UICONTROL Owner] | Indicates who owns the annotation. As a non-Admin, you can see only annotations that you own or those that were shared with you. |
| [!UICONTROL Applied Date Range] | The date or date range that this annotation applies to. |
| [!UICONTROL Shared with] | Lists how many individuals or groups that you shared the annotation with. Click for more detail. |
| [!UICONTROL Date Modified] | Shows the date and time that the annotation was last modified. |

{style="table-layout:auto"}

## Edit annotations

Editing an annotation means that you can adjust date ranges, colors, scope, or whether it applies to all report suites or projects. You can edit annotations in two ways:

* In a line chart, hover over the annotation and click the pencil icon within the popover.
* In the [!UICONTROL Annotations Manager], click the title of the annotation.

Both of these options land you back in the [!UICONTROL Annotations Builder]. There, you can make the necessary adjustments and save the new version.

## Share annotations

When sharing annotations or working with annotations that were shared with you, keep this in mind:

* If you create a project with project-only annotations, then share the project with another user, annotations cannot be edited or deleted by anyone that you share the project with.
* If you save an annotation and share it directly with a user, they can edit/delete the annotation only if they have admin rights.
* If a project is shared with you with a project-only annotation, it shows up only in that project. If the annotation is shared directly with you, it shows up in all projects where that annotation can be displayed. 

## Annotations and time zones

All annotations are created with a timestamp, but no hours or timezone information. At report time, the timezone of the panel's report suite is always applied. For example, an annotation created for Christmas Day happens on December 25 no matter what report suite timezone you are in. 

## Other annotation tasks

The Annotations manager lets Administrators edit, add, tag, delete, rename, approve, copy, export, and filter annotations. It is not visible to non-Admin users. 

Additional options are available when you select at least one annotation:

| Task | Description |
| --- | --- |
| [!UICONTROL Add] | Takes you to the Annotations builder where you can create annotations. |
| [!UICONTROL Tag] | All users can create tags for annotations and apply one or more tags to an annotation. However, you can see tags only for annotations that you own. |
| [!UICONTROL Delete] | Deleting an annotation removes it from any project in your organization. |
| [!UICONTROL Rename] | Renaming an annotation renames it in all projects that it was applied to. |
| [!UICONTROL Copy] | Creates a distinct copy with its own annotation ID, but with the same name and definition.|
| [!UICONTROL Export to CSV] | Export the annotation definition to a .csv file.|
| [!UICONTROL Filter] (left rail) | Filter by tags, report suite, owners, and other filters (Mine, Approved, Favorites, Shared with me, and Show All).|

{style="table-layout:auto"}

-->