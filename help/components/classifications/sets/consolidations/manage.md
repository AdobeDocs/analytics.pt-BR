---
title: Gerenciar Consolidações de Conjuntos de Classificações
description: Saiba como consolidar um ou mais conjuntos de classificações em um único conjunto de classificações.
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: 77599d015ba227be25b7ebff82ecd609fa45a756
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 3%

---

# Gerenciar consolidações de classificação

Caso tenha vários conjuntos de classificações que contêm dados de classificação semelhantes, é possível consolidá-los em um único conjunto de classificações. Ao consolidar dois ou mais conjuntos de classificações, o Adobe gera um novo conjunto de classificações que contém todos os dados de classificação de cada conjunto de classificações individual. As consolidações são úteis quando você faz upload de dados para muitos conjuntos de relatórios. Ou quando você tem dimensões que contêm os mesmos dados de classificação e deseja mesclá-las em um único fluxo de trabalho.

É necessário ter acesso de administrador de produto para que o Adobe Analytics veja o gerenciador de consolidação do conjunto de classificações.



Para gerenciar consolidações de classificação:

1. Selecione **[!UICONTROL Componentes]** na interface principal e **[!UICONTROL Conjuntos de classificações]**.
1. Em **[!UICONTROL Conjuntos de Classificações]**, selecione a guia **[!UICONTROL Consolidações]**.


## Gerenciador de consolidações de classificação

O gerenciador **[!UICONTROL Conjuntos de Classificações - Consolidações]** tem os seguintes elementos de interface:

![Conjuntos de Classificações - Gerenciador de Consolidações](assets/classifications-sets-consolidations.png)



### Lista de consolidações de classificação

A lista ➊ exibe consolidações de classificação que são criadas e validadas, e que podem estar sendo consolidadas. A lista tem as seguintes colunas:

| Coluna | Descrição |
|---|---|
| **[!UICONTROL Nome da Consolidação]** | O nome da consolidação dos conjuntos de classificações. |
| **[!UICONTROL Trabalho atual]** | O trabalho associado à consolidação dos conjuntos de classificações. |
| **[!UICONTROL Status]** | O status da consolidação dos conjuntos de classificações. Os valores possíveis são: **[!UICONTROL Criado]**, **[!UICONTROL Cancelado]**, **[!UICONTROL Cancelando]**, **[!UICONTROL Validação]**, **[!UICONTROL Falha na Validação]**, **[!UICONTROL Validado]**, **[!UICONTROL Comparação]**, **[!UICONTROL Falha na Comparação]**, **[!UICONTROL Consolidação]**, **[!UICONTROL Enviado]**, **[!UICONTROL Consolidação]**, **[!UICONTROL Consolidação Falha]**, **[!UICONTROL Consolidação bem-sucedida]**, **[!UICONTROL Aguardando Aprovação]**, **[!UICONTROL Finalizando]**, **[!UICONTROL Falha]** ou **[!UICONTROL Concluído]**. |
| **[!UICONTROL Hora de criação]** | O momento de criação da consolidação dos conjuntos de classificação. |
| **[!UICONTROL Hora de conclusão]** | A hora de conclusão das consolidações de classificação. |


Para redimensionar uma coluna na lista de consolidação de classificação, é possível:

* Passe o mouse sobre o separador de colunas e arraste o separador de colunas para a largura de coluna desejada.
* Selecione ![Divisa](/help/assets/icons/ChevronDown.svg) e selecione **[!UICONTROL Redimensionar coluna]**. Uma linha vertical com botão de redimensionamento permite redimensionar a coluna para o desejado com.

Para classificar uma coluna na lista de consolidação de classificação

* Selecione ![Divisa](/help/assets/icons/ChevronDown.svg) e selecione **[!UICONTROL Classificar em Ordem Crescente]** ou **[!UICONTROL Classificar em Ordem Decrescente]**. Uma seta (^ configurada) indica qual coluna e como a coluna é classificada.

### Botões Pesquisar e

Na área ➋ na parte superior da lista de consolidações de classificação, você pode:

* Pesquise ![Search](/help/assets/icons/Search.svg) para consolidações de classificação. Os resultados são mostrados na lista de consolidações de classificação. Selecione ![CrossSize200](/help/assets/icons/CrossSize200.svg) para limpar a pesquisa.
* Remova qualquer filtro aplicado à lista de consolidações de conjuntos de classificações. Selecione ![CrossSize100](/help/assets/icons/CrossSize100.svg) para remover um filtro.
* Criar uma nova consolidação de conjuntos de classificações. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]** para abrir a caixa de diálogo de consolidação dos conjuntos de classificação e definir uma nova consolidação dos conjuntos de classificação.
* Defina as colunas da lista de consolidações de classificação. Selecione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) e, na caixa de diálogo **[!UICONTROL Personalizar tabela]**, selecione as colunas a serem exibidas sob **[!UICONTROL Selecione as colunas a serem exibidas]**. Selecione **[!UICONTROL Aplicar]** para aplicar as configurações de coluna.


### Barra de ação

Ao selecionar um ou mais conjuntos de classificações na lista de conjuntos de classificações, uma barra de ação azul ➌ é exibida. As seguintes ações estão disponíveis na barra de ações:

| Ícone | Ação | Descrição |
|---|---|---|
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Editar]** | [Editar a consolidação dos conjuntos de classificações](process.md#edit-a-consolidation) |
| ![ExibirDetalhe](/help/assets/icons/ViewDetail.svg) | **[!UICONTROL Exibir]** | Exibir detalhes da consolidação do conjunto de classificações. Dependendo do status, você pode [aprovar](process.md#approve) ou [cancelar](process.md#cancel) a consolidação. |


### Painel de filtro

Selecione ![Filtro](/help/assets/icons/Filter.svg) para mostrar o painel de filtro ➍ que permite filtrar a lista de consolidações de classificação. Você pode filtrar por:

* **[!UICONTROL Status]**. Selecione um dos valores possíveis para filtrar a lista de consolidações de classificação no status. |
* **[!UICONTROL Hora de conclusão]**. Selecione um dos valores possíveis para filtrar a lista de consolidações de classificação no momento da conclusão.
* **[!UICONTROL Hora de Criação]**. Selecione um dos valores possíveis para filtrar a lista de consolidações de classificação no momento da conclusão.


Selecione ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar o painel de filtros.

Observe que os filtros mostrados no painel Filtros refletem as opções para as consolidações de classificação pré-carregadas.


<!--

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]**

Once a consolidation is run, the original classification sets are removed, with the consolidated classification set taking their place. Click **[!UICONTROL Add]** to [Create a consolidation](process.md).

## Filter classification sets

The left side of the Classification set consolidation manager provides filter settings to locate the desired consolidation. Clicking the filter icon toggles the filter settings visibility. You can filter consolidations by **[!UICONTROL Status]**, **[!UICONTROL Completion time]**, or **[!UICONTROL Creation time]**.

![Classification set consolidation filters](../../assets/classification-set-consolidation-filters.png)

Additional filter options are available above the Classification set consolidation manager columns:

* **[!UICONTROL Search by title]**: Search for consolidations by name.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Name].

## Classification set consolidation manager columns

The following columns are available in the Classification set consolidation manager:

* **[!UICONTROL Name]**: The name of the consolidation.
* **[!UICONTROL Current job]**: The current job. 
* **[!UICONTROL Status]**: The status of the consolidation. 
* **[!UICONTROL Creation date]**: The date and time that the consolidation was created.
* **[!UICONTROL Completion date]**: The date and time that the consolidation completed (or failed).

-->
