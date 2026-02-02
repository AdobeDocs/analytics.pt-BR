---
title: Gerenciar Blocos De Dados No Report Builder
description: Saiba como gerenciar blocos de dados no Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 63e169b3-7e13-405e-83a4-17f2a9917ed2
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 20%

---

# Gerenciar blocos de dados

Você pode exibir e gerenciar todos os blocos de dados em uma pasta de trabalho usando o [!UICONTROL gerenciador de blocos de dados]. O [!UICONTROL gerenciador de bloco de dados] fornece recursos de pesquisa, filtro e classificação que permitem localizar blocos de dados específicos. Após selecionar um ou mais blocos de dados, você pode editar, excluir ou atualizar os blocos de dados selecionados.

## Exibir blocos de dados

Para exibir uma tabela que lista todos os blocos de dados em uma pasta de trabalho, selecione ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**.

![A opção Gerenciar para exibir uma lista de todos os blocos de dados.](./assets/image53.png){zoomable="yes"}

O **[!UICONTROL gerenciador de bloco de dados]** mostra uma tabela com todos os blocos de dados presentes em uma pasta de trabalho.

![A lista de todos os blocos de dados presentes em uma pasta de trabalho.](./assets/image52.png){zoomable="yes"}

Você pode usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para selecionar quais colunas deseja exibir.

## Classificar blocos de dados

Você pode classificar a tabela de blocos de dados por uma coluna exibida. Por exemplo, você pode classificar blocos de dados por conjuntos de relatórios, segmentos, intervalo de datas e outras variáveis.

Para classificar a tabela de blocos de dados, selecione um cabeçalho de coluna. Selecione o mesmo cabeçalho de coluna para inverter a ordem de classificação.


## Pesquisar blocos de dados

Use o campo ![Pesquisa](/help/assets/icons/Search.svg) **[!UICONTROL _Pesquisa_]** para localizar qualquer item na tabela de blocos de dados. Por exemplo, você pode procurar métricas contidas nos blocos de dados ou no conjunto de relatórios. Também é possível pesquisar datas que estejam aparecendo nas colunas intervalo de datas, data de modificação ou data da última execução.


## Editar blocos de dados

É possível editar conjuntos de relatórios e intervalos de datas para blocos de dados. Ou os segmentos aplicados aos blocos de dados.

Por exemplo, você pode substituir um segmento existente por um novo segmento em um ou mais blocos de dados.

1. Selecione os blocos de dados que deseja atualizar. Você pode marcar a caixa de seleção de nível superior para selecionar todos os blocos de dados ou selecionar blocos de dados individuais.

   ![O ícone de edição de lápis](./assets/image56.png){zoomable="yes"}

1. Selecione ![Editar](/help/assets/icons/Edit.svg) para exibir a janela **[!UICONTROL Edição rápida]**.

   ![A janela de Edição Rápida](./assets/image58.png){zoomable="yes"}

1. Selecione um link para atualizar conjuntos de relatórios, intervalos de datas ou segmentos. Em **[!UICONTROL Edição Rápida]** - **[!UICONTROL Segmentos]**, você pode adicionar, remover ou atualizar os segmentos dos blocos de dados selecionados.

   ![O campo Adicionar segmento na janela de edição rápida](./assets/image59.png){zoomable="yes"}

## Atualizar blocos de dados

Selecione ![Atualizar](/help/assets/icons/Refresh.svg) para atualizar a tabela de blocos de dados.

Para verificar se um bloco de dados é atualizado, exiba o ícone de status de atualização:

- Um bloco de dados atualizado com êxito exibe um ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg).

- Um bloco de dados que não foi atualizado exibe um ![AlertRed](/help/assets/icons/AlertRed.svg).


## Excluir blocos de dados

Para excluir um ou mais blocos de dados:

1. Selecione um ou mais blocos de dados.
1. Clique em ![Excluir](/help/assets/icons/Delete.svg).
1. Selecione **[!UICONTROL Excluir]** na caixa de diálogo **[!UICONTROL Excluir bloco de dados]** ou **[!UICONTROL Cancelar]** para cancelar a exclusão.

## Agrupar blocos de dados

Você pode agrupar blocos de dados usando o menu suspenso **[!UICONTROL Agrupar por]** ou pode selecionar um título de coluna.

Para classificar blocos de dados por coluna, selecione o título da coluna. Para agrupar blocos de dados por grupos, selecione um nome de grupo no menu suspenso **[!UICONTROL Agrupar por]**. Por exemplo, a captura de tela abaixo mostra blocos de dados agrupados por conjunto de relatórios.

Você pode usar o agrupamento para selecionar rapidamente blocos de dados para os quais deseja modificar um elemento comum, como um segmento.

![Gerenciador de bloco de dados mostrando a lista Agrupar por Planilha.](./assets/group-data-blocks.png){zoomable="yes"}



<!--

# Manage Data Blocks in Report Builder

You can view and manage all data blocks in a workbook using the Data Block Manager. The Data Block Manager provides search, filter, and sort capabilities that allow you to quickly locate specific data blocks. After selecting one or more data blocks, you can edit, delete, or refresh the selected data blocks.

![The Data block manager screen.](./assets/image52.png)

## View Data Blocks

Click **Manage** to view a list of all data blocks in a workbook.

![The Manage option to view a list of all data blocks.](./assets/image53.png)

The Data Block Manager lists all data blocks present in a workbook. 

## Sort the Data Blocks list

You can sort the data block list by a displayed column. For example, you can sort the data block list by report suites, segments, date range, and other variables.

To sort the data block list, click a column heading.

![Sorting the data blocks.](./assets/image54.png)

## Search the Data Block list

Use the Search field to locate anything in the data block table. For example, you could search for metrics contained in the data blocks or report suite. You can also search for dates appearing in the date range, date modified, or last run date columns.

![Using the Search field to locate anything in the data block table.](./assets/image55.png)

## Edit Data Blocks

You can edit the report suite, date range, or the segments applied to one or more data blocks.

For example, you can replace an existing segment with a new segment in one or more data blocks.

1. Select the data blocks that you want to update. You can select the top-level check box to select all data blocks or you can select individual data blocks.

   ![The pencil edit icon](./assets/image56.png)

1. Click the edit icon to display the Quick edit window.

   ![The Quick edit window](./assets/image58.png)

1. Select a segment link to update report suites, date ranges, or segments.

   ![The Add Segment field in the Quick edit window](./assets/image59.png)

## Refresh Data Blocks

Click the refresh icon to refresh the data blocks in the list.

<img src="./assets/refresh-icon.png" width="15%" alt="Refresh icon"/>

To verify if a data block is refreshed, view the refresh status icon. 

A successfully refreshed data block displays a checkmark in a green circle: <img src="./assets/refresh-success.png" width="5%" alt="Green circle with check mark icon"/>. 

A data block that has failed to refresh displays a warning icon: <img src="./assets/refresh-failure.png" width="5%" alt="Red triangle with exclamation mark icon"/>.This makes it easy to identify if any data blocks have errors.


![Data block manager showing refresh status for each data block listed.](./assets/image512.png)

## Delete a Data Block

1. Select a data block in the Data Block manager. 
1. Click the trash can icon to delete the selected data block.

## Group Data Blocks

You can group data blocks using the **Group by** drop-down menu or you can click a column title. To sort data blocks by column, click the column title. To group data blocks by groups, select a group name from the **Group by** drop-down menu. For example, the screenshot below shows data blocks grouped by Sheet. It shows data blocks grouped by Sheet1 and Sheet2.  This is useful, for example, in the segment-replacing use case. If you have multiple segments applied to each data block, it is helpful to create a group containing all the data blocks that you want to replace. Then you can easily select and edit them all at once.

![Data block manager showing the Group by Sheet list.](./assets/group-data-blocks.png)

## Modify the Data Block Manager view

You can modify which columns are visible in the Data Block Manager window.


Click the column list <img src="./assets/image515.png" width="3%" alt="Column list icon"/> icon to select which columns are listed in the Data Block Manager. Select a column name to display the column. Deselect the column name to remove the column from view.

![Data block manager showing the column list](./assets/image516.png)

-->