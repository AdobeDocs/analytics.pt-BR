---
title: Criar Um Bloco De Dados No Report Builder
description: Saiba como criar um bloco de dados.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: fd3ff12a-14de-46f6-ab89-a0152fb11b0d
source-git-commit: ff1722416fe5062d16c12185d17271ebc2d6b624
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 20%

---

# Criar um bloco de dados

Um *bloco de dados* é a tabela de dados criada por uma única solicitação de dados. Uma pasta de trabalho Report Builder pode conter vários blocos de dados. Ao criar um bloco de dados, primeiro configure o bloco de dados e, em seguida, crie o bloco de dados.

## Configurar o bloco de dados

Configure os parâmetros do bloco de dados inicial para o Local do bloco de dados, Conjunto de relatórios e um Intervalo de datas.

1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**.

   ![Captura de tela mostrando a opção Criar bloco de dados](./assets/create-data-block.png){zoomable="yes"}


1. Defina a **[!UICONTROL localização do bloco de dados]**.

   A opção de localização do bloco de dados define o local da planilha no qual o Report Builder adiciona os dados à planilha.

   Para especificar o local do bloco de dados, selecione uma única célula na planilha ou insira um endereço de célula, como `a3`, `\\\$a3`, `a\\\$3` ou `sheet1!a2`. A célula especificada se torna o canto superior esquerdo do bloco de dados quando os dados são recuperados.

   Use ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) para escolher um local de bloco de dados na célula selecionada na planilha.

1. Escolha os **[!UICONTROL Conjuntos de relatórios]**.

   A opção Conjuntos de relatórios permite escolher um conjunto de relatórios a partir de um menu suspenso ou fazer referência a um conjunto de relatórios a partir do local de uma célula.

   Selecione ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) para criar um conjunto de relatórios a partir de uma célula.

1. Defina o **[!UICONTROL Intervalo de datas]**.

   A opção **[!UICONTROL Intervalo de datas]** permite escolher um intervalo de datas. Os intervalos de datas podem ser fixos ou contínuos.

   Selecione **[!UICONTROL Calendário]** para escolher um intervalo de dados usando ![Calendário](/help/assets/icons/Calendar.svg) ou insira um intervalo de datas manualmente. Como opção, você pode escolher uma predefinição no menu suspenso **[!UICONTROL _Predefinições de pesquisa_]**.

   Selecione **[!UICONTROL Da célula]** para definir dados iniciais e finais com base em uma célula na planilha atual.

   Para obter informações sobre opções de intervalo de datas, consulte [Selecionar um intervalo de datas](select-date-range.md).

1. Selecione **[!UICONTROL Próximo]**.

   ![Captura de tela mostrando a opção de intervalo de datas e o botão Próximo ativo.](./assets/choose_date_data_view3.png)

   Após configurar o bloco de dados, é possível selecionar dimensões, métricas e segmentos para criar seu bloco de dados. As guias **[!UICONTROL Dimensões]**, **[!UICONTROL Métricas]** e **[!UICONTROL Segmentos]** são exibidas acima do painel **[!UICONTROL Tabela]**.

## Criar o bloco de dados

Para criar o bloco de dados, selecione componentes do relatório e personalize o layout.

1. Adicionar componentes de **[!UICONTROL Dimensões]**, **[!UICONTROL Métricas]** e **[!UICONTROL Segmentos]**.

   Rolar as listas de componentes ou usar o campo ![Pesquisar](/help/assets/icons/Search.svg) **[!UICONTROL _Pesquisar componentes_]** para localizar componentes. Arraste e solte componentes no painel [!UICONTROL Tabela] ou selecione duas vezes um nome de componente na lista para adicionar o componente ao painel [!UICONTROL Tabela].

   Selecione duas vezes um componente para adicioná-lo a uma seção padrão da tabela.

   - Os componentes do Dimension são adicionados à seção ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]** ou à seção ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]** se você já tiver uma dimensão nas colunas.
   - Os componentes de data são adicionados à seção ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**.
   - Componentes de segmento são adicionados à seção ![Segmentação](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmentos]**.
   - Os componentes de métricas são adicionados à seção ![Valores](/help/assets/icons/Event.svg) de **[!UICONTROL de]** Eventos.

1. Organize os itens no painel Tabela para personalizar o layout do bloco de dados.

   Arraste e solte componentes em cada lista no painel Tabela para reordenar componentes ou selecione ![MaisPequeno](/help/assets/icons/MoreSmall.svg) e selecione ![SetaParaCima](/help/assets/icons/ArrowUp.svg) Mover para cima, ![SetaParaBaixo](/help/assets/icons/ArrowDown.svg) Mover para baixo e muito mais para mover componentes dentro de uma lista.

   Quando você adiciona componentes à tabela, uma pré-visualização do bloco de dados é exibida no local do bloco de dados na planilha. O layout da pré-visualização do bloco de dados é atualizado automaticamente à medida que você adiciona, move ou remove itens na tabela.

   ![Captura de tela mostrando os componentes adicionados e a planilha atualizada.](./assets/image10.png)


1. Opcionalmente, defina a **[!UICONTROL Data inicial]** como uma dimensão para identificar a data inicial do bloco de dados. Adicionar os dados iniciais como uma dimensão é útil se você tiver um relatório agendado regularmente que tenha um intervalo de datas em andamento. Ou se você tiver um intervalo de datas não convencional e precisar ser explícito sobre a data de início.

   ![Captura de tela mostrando a data de início na lista de dimensões.](./assets/start-date-dimension.png)

1. Opcionalmente, exibir ou ocultar cabeçalhos de linha e coluna. Para fazer isso:

   1. Selecione o ícone de configurações **[!UICONTROL Tabela]** ![Configuração](/help/assets/icons/Setting.svg)configurações.

      ![Captura de tela mostrando a opção de configurações de Tabela.](./assets/table-settings.png)

   1. Marque ou desmarque a opção para **[!UICONTROL Exibir cabeçalhos de linha e coluna]**. Os cabeçalhos são exibidos por padrão.

1. Como opção, também é possível ocultar ou mostrar rótulos de dimensão e cabeçalhos de métrica. Para fazer isso:

   1. Selecione ![MaisPequena](/help/assets/icons/MoreSmall.svg) no rótulo da dimensão ou no cabeçalho da coluna para exibir o menu de contexto.

      ![O ícone de reticências na seção Linha.](./assets/row-heading.png)

   1. Selecione ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** ou ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** para alternar o rótulo da dimensão ou o cabeçalho da coluna. Todos os rótulos são exibidos por padrão.

1. Selecione **[!UICONTROL Concluir]** para concluir a configuração do bloco de dados.

1. Uma mensagem de processamento **[!UICONTROL #BUSY]** é exibida enquanto os dados de análise são recuperados.

   ![A mensagem de processamento.](./assets/image11.png)

1. O Report Builder recupera os dados e exibe o bloco de dados concluído na planilha.

   ![O bloco de dados concluído.](./assets/image12.png)


>[!MORELIKETHIS]
>
>[Selecione um conjunto de relatórios](select-report-suite.md)
>[Selecionar um intervalo de datas](select-date-range.md)
>[Filtrar dimensões](filter-dimensions.md)
>[Trabalhar com segmentos](work-with-segments.md)
>


<!--

A *data block* is the table of data created by a single data request. A Report Builder workbook can contain multiple data blocks. When you create a data block, first configure the data block and then build the data block.

## Configure the data block

Configure the initial data block parameters for the data block location, report suite, and a date range.

1. Click **[!UICONTROL Create]**.

    ![Screenshot showing the Create data block option.](./assets/create_db.png)

1. Set the **[!UICONTROL Data block location]**.

    The data block location option defines the worksheet location where report builder adds the data to your worksheet.

    To specify the data block location, select a single cell in the worksheet and click the icon next to **[!UICONTROL Data block location]**: 
    
    You can also enter a cell address such as a3, \\\$a3, a\\\$3 or sheet1!a2. The cell specified marks the upper-left corner of the data block when the data is retrieved.

1. Choose a **Report Suite**.

    The report suites option allows you to choose a report suite from a drop-down menu or to reference a report suite from a cell location.

1. Set the **[!UICONTROL Date range]**.

    The Date range option allows you to choose a date range. Date ranges may be fixed or rolling. For information about data range options, see [Select a Date Range](select-date-range.md).

1. Click **[!UICONTROL Next]**.

    ![Screenshot showing the date range option and the active Next button.](./assets/choose_date_report_suite.png)

    After you configure the data block, you can select dimensions, metrics, and segments to build your data block. The Dimensions, Metrics, and Filters tabs are displayed above the Table builder pane.

## Build the data block

To build the data block, select report components, and then customize the layout.

1. Add Dimensions, Metrics, and Segments.

    Scroll the component lists or use the **[!UICONTROL Search]** field to locate components. Drag and drop components to the Table pane or double-click a component name in the list to automatically add the component to the Table pane.

    Double-click a component to add it to a default section of the table.

    - Dimension components are added to the Row section or to the Column section if you have a dimension already in the columns.
    - Date components are added to the Column section.
    - Segment components are added to the Segments section.

    **Start date as a Dimension**

    Set the **[!UICONTROL Start date]** as a dimension to clearly identify the start date of your data block. This is helpful if you have a regularly scheduled report that has a rolling date range or if you have an unconventional date range and you need to be clear on the start date.

    ![Screenshot showing the Start date in the list of dimensions.](./assets/start-date-dimension.png){width="30%"}

1. Arrange the items in the Table pane to customize the layout of your data block.

    Drag and drop components in the Table pane to reorder components or right-click a component name and select from the options menu.

    When you add components to the table, a preview of the data block is displayed at the Data block location in the worksheet. The layout of the data block preview automatically updates as you add, move, or remove items in the table.

    ![Screenshot showing the added components and updated worksheet.](./assets/image10.png)

    **Display or hide row and column headers**

1. Click the **[!UICONTROL Table settings]** icon.

    ![Screenshot showing the Table settings option.](./assets/table-settings.png){width="35%"}

1. Check or uncheck the option to Display row and column headers. The headers are displayed by default.

    **Hide or show dimension labels and metric headers**

1. Click the ellipsis icon on either the dimensions or the column headers to display the settings.

    ![The ellipsis icon in the Row section.](./assets/row-heading.png){width="35%"}

1. Click Hide or Show to toggle the dimension labels or column headers. All labels are displayed by default.

1. Click **[!UICONTROL Finish]**.

    A processing message is displayed while the analytics data is retrieved.

    Report Builder retrieves the data and displays the completed data block in the worksheet.

    ![The completed data block.](./assets/image12.png)

-->