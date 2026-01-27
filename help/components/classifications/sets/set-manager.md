---
title: Gerenciar conjuntos de classificações
description: Gerenciar conjuntos de classificações no Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: d5e1432569516d13d2de30a2cb30cebb067ab783
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 5%

---

# Gerenciar conjuntos de classificação

É possível criar, renomear, editar, consolidar, excluir e marcar conjuntos de classificações na interface de gerenciamento de conjuntos de classificações. Também é possível filtrar e pesquisar por conjuntos de classificações específicos.

Para gerenciar conjuntos de classificações:

1. Selecione **[!UICONTROL Componentes]** na barra de menu superior do Adobe Analytics e selecione **[!UICONTROL Conjuntos de classificações]**.
1. Em **[!UICONTROL Conjuntos de classificações]**, selecione a guia **[!UICONTROL Conjuntos de classificações]**.

## Gerenciador de conjuntos de classificações

O gerenciador **[!UICONTROL Conjuntos de Classificações]** tem os seguintes elementos de interface:

![Gerenciador de conjuntos de classificação](assets/classification-sets-manage.png)


### Lista de conjuntos de classificações

A lista **[!UICONTROL de]** Conjuntos de classificações➊ exibe todos os conjuntos de classificações. A lista tem as seguintes colunas:

| Coluna | Descrição |
|---|---|
| **[!UICONTROL Conjunto de classificações]** | O nome do conjunto de classificações. Selecione o nome para [editar o conjunto de classificações](create.md#edit-a-classification-set). |
| **[!UICONTROL Subscrições]** | O número de assinaturas ao qual o conjunto de classificações se aplica. |
| **[!UICONTROL Classificações]** | O número de dimensões de classificação que o conjunto de classificações contém. |
| **[!UICONTROL Automatizado]** | O conjunto de classificações está configurado para importar dados de um local na nuvem automaticamente ou não? Essa automação pode ser configurada como parte do [esquema de conjuntos de classificações](manage/schema.md). |
| **[!UICONTROL Última modificação]** | O carimbo de data e hora da última modificação do conjunto de classificações. |

Para redimensionar uma coluna na lista de conjuntos de classificações, é possível:

* Passe o mouse sobre o separador de colunas e arraste o separador de colunas para a largura de coluna desejada.
* Selecione ![Divisa](/help/assets/icons/ChevronDown.svg) e selecione **[!UICONTROL Redimensionar coluna]**. Uma linha vertical com botão de redimensionamento permite redimensionar a coluna para o desejado com.

Para classificar uma coluna na lista de conjuntos de classificações

* Selecione ![Divisa](/help/assets/icons/ChevronDown.svg) e selecione **[!UICONTROL Classificar em Ordem Crescente]** ou **[!UICONTROL Classificar em Ordem Decrescente]**. Uma seta (^ configurada) indica qual coluna e como a coluna é classificada.

### Botões Pesquisar e

Na área ➋ na parte superior da lista de conjuntos de classificações, você pode:

* Pesquise ![Search](/help/assets/icons/Search.svg) por conjuntos de classificações. Os resultados são mostrados na lista de conjuntos de classificação. Selecione ![CrossSize200](/help/assets/icons/CrossSize200.svg) para limpar a pesquisa.
* Remova qualquer filtro aplicado à lista de conjuntos de classificações. Selecione ![CrossSize100](/help/assets/icons/CrossSize100.svg) para remover um filtro.
* Selecione ![MaisCírculo](/help/assets/icons/MoreCircle.svg) para carregar mais 1000 conjuntos de classificações. Inicialmente, a lista do conjunto de classificações exibe até 1000 conjuntos de classificações.
* Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]** para [criar um novo conjunto de classificações](create.md#create-a-classification-set).
* Defina as colunas da lista do conjunto de classificações. Selecione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) e, na caixa de diálogo **[!UICONTROL Personalizar tabela]**, selecione as colunas a serem exibidas sob **[!UICONTROL Selecione as colunas a serem exibidas]**. Selecione **[!UICONTROL Aplicar]** para aplicar as configurações de coluna.


### Barra de ação

Ao selecionar um ou mais conjuntos de classificações na lista de conjuntos de classificações, uma barra de ação azul ➌ é exibida. As seguintes ações estão disponíveis na barra de ações:

| Ícone | Ação | Descrição |
|---|---|---|
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Editar]** | [Edite o conjunto de classificações](create.md#edit-a-classification-set) no construtor de conjuntos de classificações. |
| ![Renomear](/help/assets/icons/Rename.svg) | **[!UICONTROL Renomear]** | Renomear um conjunto de classificações.<br/>Na caixa de diálogo **[!UICONTROL Renomear: _conjunto de classificações_]**, digite um novo nome e selecione **[!UICONTROL Renomear]**. |
| ![Mesclar](/help/assets/icons/Merge.svg) | **[!UICONTROL Consolidar]** | [Consolidar conjuntos de classificações](/help/components/classifications/sets/consolidations/manage.md). |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Excluir um conjunto de classificações.<br/>O **[!UICONTROL Excluir _conjunto de classificações_?A caixa de diálogo]** aparece. A exclusão de um conjunto de classificações não pode ser desfeita. Qualquer projeto ou consolidação agendada que use esse conjunto de classificações continuará a usar a definição desse conjunto de classificações até que você salve novamente os projetos agendados ou revalide as consolidações agendadas. Selecione **[!UICONTROL Excluir]** para excluir o conjunto de classificações. |
| ![Rótulo](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Marcar o conjunto de classificações.<br/>Na caixa de diálogo **[!UICONTROL Marca: _conjunto de classificações_]**, selecione uma ou mais marcas no menu suspenso **[!UICONTROL Marcas]**&#x200B;para adicionar marcas. Ou insira uma ou mais tags novas. Use ![CrossSize100](/help/assets/icons/CrossSize100.svg) para remover uma marca. <br/>Selecione **[!UICONTROL Salvar]**&#x200B;para salvar as marcas. |


### Painel de filtro

Selecione ![Filtro](/help/assets/icons/Filter.svg) para mostrar o painel de filtro ➍ que permite filtrar a lista de conjuntos de classificações. Você pode filtrar por:

* **[!UICONTROL Tags]**. Selecione uma ou mais tags para filtrar a lista de conjuntos de classificações nas tags.
* **[!UICONTROL Conjunto de Relatórios]**. Selecione um ou mais conjuntos de relatórios para filtrar a lista de conjuntos de classificações em conjuntos de relatórios.

Selecione ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar o painel de filtros.

Observe que os filtros mostrados no painel Filtros refletem as opções dos conjuntos de classificações pré-carregados.


<!-- old content

The Classification set manager allows you to create, edit, or delete classification sets.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]**

Classification sets consist of **Subscriptions** (report suite and dimension combinations) and **Classification names** (dimensions containing classification data). Subscriptions are configured under [Settings](settings.md), while classification names are configured under [Schema](schema.md).

## Filter classification sets

The left side of the Classification set manager provides filter settings to locate the desired classification set. Clicking the filter icon toggles the filter settings visibility. You can filter classification sets by **[!UICONTROL Tags]** or **[!UICONTROL Report suite]**.

![Classification set filters](../../assets/classification-set-filters.png)

Note that 1,000 classification sets are preloaded at a time. The filters shown in the left rail reflect the options for the sets that are preloaded.

## Classification set manager columns

The following columns are available in the Classification set manager:

* **[!UICONTROL Classification set]**: The classification set name. Clicking a classification set name edits its [settings](settings.md).
* **[!UICONTROL Subscriptions]**: The number of subscriptions that this classification set applies to.
* **[!UICONTROL Classifications]**: The number of classification dimensions that the classification set contains.
* **[!UICONTROL Automated]**: Determines if the classification set is configured to automatically import data from a cloud location. Automation can be configured in the classification set's [schema](schema.md).
* **[!UICONTROL Last Modified]**: The date and time that the classification set was last modified.

## Create or edit options

The following buttons are available in the Classification set manager:

* **[!UICONTROL Add]**: [Create](create.md) a classification set.
* **[!UICONTROL Search by title]**: Search for classification sets by name.
* **[!UICONTROL Load more]**: The Classification set manager initially displays up to 1000 classification sets. This button loads 1000 more classification sets.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Classification set].

Select one or more classification sets by clicking the checkbox next to the desired classification set. Selecting a classification set reveals the following options:

* **[!UICONTROL Tag]**: Add one or more tags to the selected classification sets, which allows you to organize or group classification sets to make them easier to locate in the future.
* **[!UICONTROL Delete]**: Deletes the classification set. Classification dimensions based on this classification set are no longer available. Scheduled projects using the deleted classification set continue using dependent dimensions until you resave the scheduled project.
* **[!UICONTROL Consolidate]**: Start a new [consolidation](../consolidations/process.md).
* **[!UICONTROL Rename]**: Rename the selected classification set.

-->