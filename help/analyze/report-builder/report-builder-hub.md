---
title: O Hub do Report Builder
description: Saiba mais sobre o hub do Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: e18381ea-b7d4-4d7a-9ded-23b2d06fa204
source-git-commit: ff1722416fe5062d16c12185d17271ebc2d6b624
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 22%

---

# Central do Report Builder


O hub do Report Builder é o painel direito exibido em sua pasta de trabalho do Excel quando você seleciona ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** na barra da faixa de opções do Excel.

Use o hub do Report Builder para criar, atualizar, excluir e gerenciar blocos de dados.

O hub do Report Builder contém os botões ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**, ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** e ![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]**, o painel **[!UICONTROL Commands]** e o painel **[!UICONTROL Edição rápida]**.

![hub do Report Builder](assets/hub51.png){zoomable="yes"}


Selecionar

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]** to [create new data blocks](create-a-data-block.md).
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** para [gerenciar blocos de dados existentes](manage-reportbuilder.md).
* ![Calendário](/help/assets/icons/Calendar.svg) **[!UICONTROL Agendar]** para [gerenciar agendas para enviar sua pasta de trabalho por email](schedule-reportbuilder.md).

## Painel Comandos

Use o painel **[!UICONTROL Comandos]** para acessar comandos compatíveis com as células selecionadas ou uma ação anterior.

| Comandos | Disponível quando... | Propósito |
|------|------------------|--------|
| ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar bloco de dados]** | O intervalo de célula ou células selecionado faz parte de apenas um bloco de dados. | Use para editar um bloco de dados. |
| ![Atualizar](/help/assets/icons/Refresh.svg) **[!UICONTROL Atualizar bloco de dados]** | A seleção contém pelo menos um bloco de dados. O comando atualiza somente os blocos de dados na seleção. | Use para atualizar um ou mais blocos de dados. |
| ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Atualizar todos os blocos de dados]** | A pasta de trabalho contém um ou mais blocos de dados. | Usar para atualizar todos os blocos de dados na pasta de trabalho |
| ![Enviar](/help/assets/icons/Send.svg) **[!UICONTROL Enviar pasta de trabalho]** | A pasta de trabalho contém um ou mais blocos de dados. | Use para [enviar a pasta de trabalho como um arquivo por email](schedule-reportbuilder.md). |
| ![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar bloco de dados]** | A célula ou o intervalo de células selecionado faz parte de um ou mais blocos de dados. | Use para copiar um bloco de dados. |
| ![Recortar](/help/assets/icons/Cut.svg) **[!UICONTROL Recortar bloco de dados]** | A célula ou o intervalo de células selecionado faz parte de um ou mais blocos de dados. | Use para recortar um bloco de dados. |
| ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir bloco de dados]** | O intervalo de célula ou células selecionado faz parte de apenas um bloco de dados. | Usar para excluir um bloco de dados |

## Painel de edição rápida

Ao selecionar um ou mais blocos de dados em uma planilha, o Report Builder exibe o painel **[!UICONTROL Edição rápida]**. Você pode usar o painel **[!UICONTROL Edição rápida]** para alterar parâmetros em um ou mais blocos de dados ao mesmo tempo.

As alterações feitas ao usar as seções de **[!UICONTROL Edição Rápida]** se aplicam a todos os blocos de dados selecionados.

### Conjuntos de relatórios

Os blocos de dados extraem dados de um conjunto de relatórios selecionado. Se vários blocos de dados forem selecionados em uma planilha, e caso eles não extraiam dados do mesmo conjunto de relatórios, o link **Conjuntos de relatórios** exibe **[!UICONTROL _Vários_]**.

Quando você altera o conjunto de relatórios, todos os blocos de dados na seleção adotam o novo conjunto de relatórios. Os componentes no bloco de dados são correspondidos ao novo conjunto de relatórios com base na ID. Se um componente não for encontrado em um bloco de dados, ele será removido e substituído por **[!UICONTROL Valor inválido]** ou um ![AlertRed](/help/assets/icons/AlertRed.svg) será exibido para o componente específico.

Para alterar o conjunto de relatórios, selecione um novo conjunto de relatórios no menu suspenso **[!UICONTROL Conjunto de relatórios]**.


### Intervalo de datas

**Intervalo de datas** mostra o intervalo de datas dos blocos de dados selecionados. Se vários blocos de dados forem selecionados com vários intervalos de datas, o link **[!UICONTROL Intervalo de datas]** exibirá **[!UICONTROL _Vários_]**.

### Segmentos

O link **Segmentos** exibe uma lista de resumo dos segmentos usados pelos blocos de dados selecionados. Se vários blocos de dados forem selecionados com vários segmentos aplicados, o link **Segmentos** exibirá **[!UICONTROL _Vários_]**.

>[!MORELIKETHIS]
>
>[Selecione um conjunto de relatórios](select-report-suite.md)
>[Selecionar um intervalo de datas](select-date-range.md)
>[Trabalhar com filtros](work-with-segments.md)
>

<!--

Use the Report Builder hub to create, update, delete, and manage data blocks.

The Report Builder hub contains the Create, Manage, and Schedule buttons, the COMMANDS panel, and The QUICK EDIT panel.

<img src="./assets/hub51.png" alt="Report Builder Hub"/>


## Create, Manage, and Schedule buttons

Use the Create, Manage, and Schedule buttons to create new data blocks, manage existing data blocks, or schedule datablocks.

## COMMANDS panel

Use the COMMANDS panel to access commands that are compatible with the selected cells or a previous action.

### Commands

| Commands displayed      | Available when…   | Purpose          |
|------|------------------|--------|
| Edit data block | The selected cell or cells range is part of one data block only. | Used to edit a data block |
| Refresh data block | The selection contains at least one data block. The command refreshes only the data blocks in the selection. | Used to refresh one or more data blocks |
| Refresh all data blocks | The workbook contains one or more data blocks. | Used to refresh ALL data blocks in the workbook |
| Send workbook |   |  Send a workbook on a schedule. |
| Copy data block   | The selected cell or cell range is part of one or more data blocks. | Used to copy a data block   |
| Cut data block |   | Used to cut a data block |
| Delete data block | The selected cell or cells range is part of one data block only. | Used to delete a data block |

## QUICK EDIT panel

When you select one or more data blocks in a spreadsheet, Report Builder displays the QUICK EDIT panel. You can use the QUICK EDIT panel to change parameters in a single data block or to change parameters in multiple data blocks at the same time.

![The Quick Edit panel in Report Builder](./assets/hub2.png)

The changes made using the Quick Edit sections apply to all selected data blocks.

### Report suites

Data blocks pull data from a selected report suite. If multiple data blocks are selected in a worksheet and they don't pull data from the same report suite, the **Report Suites** link displays *Multiple*.

When you change the report suite, all data blocks in the selection adopt the new report suite. Components in the data block are matched to the new report suite based on ID, for example, matching ```evars```). If a component isn't found in a data block, a warning message is displayed and the component is removed from the data block.

To change the report suite, select a new report suite from the drop-down menu.

![The Report Builder Hub showing the report suite drop-down menu.](./assets/image16.png)

### Date range

**[!UICONTROL Date range]** shows the date range for the selected data blocks. If multiple data blocks are selected with multiple date ranges, the **[!UICONTROL Date range]** link displays *Multiple*. [Learn more](/help/analyze/report-builder/select-date-range.md)

### Segments

The **Segments** link displays a summary list of the segments used by the selected data blocks. If multiple data blocks are selected with multiple segments applied, the **Segments** link displays *Multiple*. [Learn more](/help/analyze/report-builder/work-with-segments.md)

-->