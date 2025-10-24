---
title: Criar conjuntos de classificações
description: Saiba como criar campos e descrições disponíveis ao criar um conjunto de classificações.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 77599d015ba227be25b7ebff82ecd609fa45a756
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 2%

---

# Criar e editar conjuntos de classificações

Você [cria](#create-a-classification-set) e [edita](#edit-a-classification-set) conjuntos de classificações a partir do gerenciador de Conjuntos de Classificações.

## Criar um conjunto de classificação

Para criar um conjunto de classificações, na interface principal:

1. Selecione **[!UICONTROL Componentes]** na interface principal e **[!UICONTROL Conjuntos de classificações]**.
1. Em **[!UICONTROL Conjuntos de classificações]**, selecione a guia **[!UICONTROL Conjuntos de classificações]**.
1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]**.
1. Na caixa de diálogo **[!UICONTROL Adicionar novo conjunto de classificações]**:

   ![Conjuntos de classificações - Adicionar novo conjunto de classificações](assets/classifications-sets-new.png)

   1. Insira um **[!UICONTROL Nome]**. Por exemplo: `Classification Set Example`.
   1. Insira uma **[!UICONTROL Descrição (opcional)]**. Por exemplo, `Example classification set`.
   1. Insira um ou mais endereços de email (separados por vírgula) em **[!UICONTROL Notificação de problemas]**. Notificações por email são enviadas a esses usuários sobre problemas.
   1. Selecione o **[!UICONTROL Tipo]** do conjunto de classificações. Os possíveis tipos são:
      * **[!UICONTROL Primário]**. Um conjunto de classificações principal se aplica às dimensões coletadas no Adobe Analytics. As classificações primárias são uma maneira de agrupar (classificar) valores de dimensão granulares em níveis de dados mais significativos. Por exemplo, talvez você queira agrupar palavras-chave de pesquisa interna em categorias de pesquisa interna, para compreender temas em seus dados de pesquisa. Ou classificar SKUs do produto por cor ou categoria.
         * Insira uma ou mais **[!UICONTROL Assinaturas]**.  Você pode definir várias combinações do **[!UICONTROL Conjunto de relatórios]** e do **[!UICONTROL Dimension]** para um conjunto de classificações.

         * Selecione ![CrossSize400](/help/assets/icons/CrossSize400.svg) para excluir uma combinação do **[!UICONTROL Conjunto de Relatórios]** e do **[!UICONTROL Key Dimension]**.

        Se você adicionar uma combinação do **[!UICONTROL Conjunto de relatórios]** e da **[!UICONTROL Chave do Dimension]** que já existe em outro conjunto de classificações, você verá um alerta vermelho abaixo da combinação. Você pode selecionar **[!UICONTROL Adicionar ao existente]** para abrir o outro conjunto de classificações e [adicionar classificações ao esquema](schema.md) para esse outro conjunto de classificações ou alterar a dimensão.
      * **[!UICONTROL Pesquisa]**. Geralmente chamada de subclassificação ou secundária, uma tabela de pesquisa é uma classificação de uma classificação principal. Uma pesquisa consiste em metadados sobre um valor de classificação, em vez da dimensão original. Por exemplo, uma dimensão de *Produto* pode ter uma classificação principal de *Código de cor*. Uma tabela de pesquisa com o *Nome da cor* poderia ser anexada ao *Código de cor* para explicar cada código de cor.
1. Selecione **[!UICONTROL Salvar]** para salvar o conjunto de classificações. Selecione **[!UICONTROL Cancelar]** para cancelar a definição.
1. Para definir o esquema para o conjunto de classificação, selecione o conjunto de classificações recém-criado no gerenciador **[!UICONTROL Conjuntos de Classificações]** para [editar o conjunto de classificações](#edit-a-classification-set).


## Editar um conjunto de classificações

Para editar um conjunto de classificações, na interface principal:

1. Selecione **[!UICONTROL Componentes]** na interface principal e **[!UICONTROL Conjuntos de classificações]**.
1. Em **[!UICONTROL Conjuntos de classificações]**, selecione a guia **[!UICONTROL Conjuntos de classificações]**.
1. Selecione o título do seu conjunto de classificações.
1. Na caixa de diálogo **[!UICONTROL Conjunto de classificações: _título do conjunto de classificações_]**, você pode definir as [configurações](settings.md) e o [esquema](schema.md) para o conjunto de classificações.
1. Depois de concluído, selecione **[!UICONTROL Salvar]** para salvar suas alterações. Selecione **[!UICONTROL Cancelar]** para cancelar.


<!--


### Schema

In the Schema tab 





You can use the Classification set manager to create a classification set.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

When creating a classification set, the following fields are available.

* **[!UICONTROL Name]**: A text field used to identify the classification set. This field cannot be edited upon creation, but can be renamed later.
* **[!UICONTROL Column Name]**: The name of the first classification dimension that you want to create. This field is the dimension name used in Analysis Workspace, and the column name when exporting classification data. You can add more column names after the classification set is created.
* **[!UICONTROL Type]**: Radio buttons that indicate the type of classification.
  * **[!UICONTROL Primary]**: Apply to dimensions collected in Analytics. They are a way to group (classify) granular dimension values into more meaningful levels of data. For example, you might want to group internal search keywords into internal search categories, to better understand themes in your search data.
  * **[!UICONTROL Lookup]**: Commonly referred to as child or subclassifications, a lookup table is a classification of a primary classification. It is metadata about a classification value, rather than the original dimension. For example, the Product variable might have a primary classification of 'Color code'. A lookup table of 'Color name' could then be attached to 'Color code' to further explain what each code means.
* **[!UICONTROL Subscriptions]** The report suites and dimensions that this classification set applies to. You can add multiple report suite and dimension combinations to a classification set.

![Create a Classification set](../../assets/classification-set-create.png)

If a classification set exists for a given report suite + variable, the classification is added to the schema instead. A given report suite + variable combination cannot belong to multiple classification sets.

-->