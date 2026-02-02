---
title: Selecionar Um Intervalo De Dados No Report Builder
description: Saiba como selecionar um intervalo de datas no Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 610ce2c8-8ff6-4434-912f-3015cc56a51e
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 46%

---

# Selecionar um intervalo de datas

Para alterar o intervalo de datas de um bloco de dados existente:

- Selecione **[!UICONTROL Editar um bloco de dados]** ou
- Selecione o link **[!UICONTROL Intervalo de datas]** em **[!UICONTROL Edição rápida]**.

Use as seguintes opções para alterar um intervalo de datas para um bloco de dados.

## Calendário

A opção **[!UICONTROL Calendário]** permite criar datas estáticas ou contínuas usando estas opções:

### Intervalo de datas

O campo Intervalo de datas exibe o intervalo de datas atual para a solicitação de bloco de dados. Você pode inserir datas diretamente ou usar o ![Calendário](/help/assets/icons/Calendar.svg) para especificar um intervalo de datas.

![Calendário de intervalo de datas](assets/date-range-calendar.png){zoomable="yes"}

### Predefinições

Use o menu suspenso Predefinições para selecionar uma predefinição. Também é possível digitar texto para procurar predefinições.

![Predefinições de intervalo de datas](assets/date-range-presets.png){zoomable="yes"}

O menu suspenso predefinido inclui um conjunto padrão de intervalos de datas predefinidos e componentes de intervalo de datas para um conjunto de relatórios salvo ou para um conjunto de relatórios que foi compartilhado com você.

### Datas do acumulado

Para definir datas do acumulado:

![Datas do acumulado](assets/date-range-rolling-date.png){zoomable="yes"}

1. Selecione **[!UICONTROL Usar datas do acumulado]** para definir a lógica de uma definição de data do acumulado. É possível selecionar o texto entre parênteses (por exemplo, **[!UICONTROL início fixo - rolagem diária]**) para estender o painel e especificar detalhes para **[!UICONTROL Início]** e **[!UICONTROL Fim]**.

1. Selecione **[!UICONTROL Início de]**, **[!UICONTROL Fim de]** ou **[!UICONTROL Dia fixo]**.

   - Ao selecionar **[!UICONTROL Início de]** ou **[!UICONTROL Fim de]**, você pode criar uma expressão completa. Por exemplo: **[!UICONTROL Fim do]** **[!UICONTROL ano atual]** **[!UICONTROL mais]** `1` **[!UICONTROL dia]**. Escolha o valor apropriado para cada parte individual da expressão.

      - Selecione um valor para o atual. Por exemplo, **[!UICONTROL ano atual]**.
      - Selecione um valor para um cálculo adicional opcional. Por exemplo, **[!UICONTROL mais]**.
      - Após definir um cálculo adicional, especifique um valor. Por exemplo, `1`.
      - Depois de especificar um cálculo adicional, selecione o período a ser usado para o cálculo. Por exemplo, **[!UICONTROL dia]**.

   - Ao selecionar **[!UICONTROL Dia Fixo]**, especifique um dia fixo ou use o seletor para selecionar um dia.

1. Selecione **[!UICONTROL ocultar]** para ocultar os detalhes do cálculo das datas do acumulado.


### Expressões personalizadas

A opção de expressão personalizada permite alterar o intervalo de datas, criando uma expressão personalizada ou possibilitando a inserção de uma fórmula aritmética.

![Expressão personalizada de intervalo de datas](assets/date-range-custom-expression.png){zoomable="yes"}

1. Selecionar **[!UICONTROL Usar datas do acumulado]**.

1. Selecionar **[!UICONTROL Usar expressão personalizada]**.

   Ao selecionar **[!UICONTROL Usar expressão personalizada]**, os controles padrão de intervalo de datas do acumulado são desabilitados.

1. Insira uma [expressão personalizada](#create-a-custom-expression).

1. Use a **[!UICONTROL Visualização de data]** para verificar o intervalo de datas resultante.

#### Criar uma expressão personalizada

1. Insira uma [referência de data](#date-references).

1. Adicione um [operador de data](#date-operators) opcional para mover a data para o passado ou futuro.

Você pode inserir uma expressão personalizada que inclua vários operadores, como `tm-11m-1d`.

#### Referências de data

A tabela a seguir lista exemplos de referência de data.

| Referência de data | Tipo | Descrição |
|----------------|--------------|----------------------------|
| `1/1/10` | Data estática | Inserido no formato de Data ISO |
| `td` | Data do acumulado | Início do dia atual |
| `tw` | Data do acumulado | Início da semana atual |
| `tm` | Data do acumulado | Início do mês atual |
| `tq` | Data do acumulado | Início do trimestre atual |
| `ty` | Data do acumulado | Início do ano atual |

#### Operadores de data

A tabela a seguir lista exemplos de operadores de data.

| Operador de data | Unidade | Descrição |
|----------------|---------|--------------------|
| `+6d` | Dia | Adicionar 6 dias à referência de data |
| `+1w` | Semana | Adicionar uma semana inteira à referência de data |
| `-2m` | Mês | Subtrair 2 meses completos da referência da data |
| `-4q` | Trimestre | Subtrair 4 trimestres da referência de data |
| -`1y` | Ano | Subtrair um ano da referência de data |

#### Expressões de datas

A tabela a seguir lista exemplos de expressão de data.

| Expressão de data | Significado |
|-----------------|--------------------------------------|
| `td` | Hoje |
| `td-1w` | Primeiro dia da semana passada |
| `tm-1d` | Último dia do mês anterior |
| `td-52w` | Mesmo dia 52 semanas atrás |
| `tm-11m-1d` | Último dia do mesmo mês do ano passado |
| `"2020-09-06"` | Data específica, 9 de setembro de 2020 |



## Intervalo de datas da célula

O intervalo de datas pode ser especificado em células da planilha. Use a opção **[!UICONTROL Intervalo de datas da célula]** para escolher a data inicial e final do bloco de dados a partir das células selecionadas. Ao selecionar a opção **[!UICONTROL Da célula]**, o painel exibe os campos **[!UICONTROL De]** e **[!UICONTROL Para]**, nos quais você pode inserir um local de célula ou usar ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) para escolher a célula selecionada no momento.

![Selecionar da célula Folha1!H4 para Folha1!I4](./assets/date-range-from-cell.png){zoomable="yes"}


## Excluir hoje

Selecione **[!UICONTROL Excluir hoje]** para excluir hoje de um intervalo de datas selecionado. O dia atual é excluído de todos os modos usados para definir um intervalo de datas: calendário, datas do acumulado ou expressões personalizadas.


## Intervalos de datas válidos

A lista a seguir descreve formatos válidos de intervalo de datas.

- As datas inicial e final devem estar no seguinte formato: AAAA-MM-DD

- A data inicial deve ser anterior ou igual à data final. Ambas as datas podem ser definidas para o futuro.

- Ao usar datas em andamento, a data inicial deve ser hoje ou no passado. O dia de início deve estar no passado se **[!UICONTROL Excluir hoje]** estiver selecionado.

- É possível criar um intervalo de datas estático para o futuro. Por exemplo, talvez seja necessário definir uma data futura para um lançamento de campanha de marketing na próxima semana. Essa opção cria um monitoramento de pasta de trabalho para uma campanha antecipadamente.

## Alterar intervalo de datas

É possível editar o intervalo de datas de um bloco de dados existente.

1. Selecione uma célula em seu bloco de dados.

- Selecione **[!UICONTROL Editar bloco de dados]** no painel **[!UICONTROL Comandos]** ou
- Selecione o link **[!UICONTROL Intervalo de datas]** no painel **[!UICONTROL Edição rápida]**.

1. Modifique o intervalo de datas usando qualquer uma das opções de seleção de data disponíveis.

1. Selecione **[!UICONTROL Aplicar]**.

O Report Builder aplica o novo intervalo de datas a todos os blocos de dados na seleção.

<!--
To change the date range of an existing data block, select Edit a data block or use the QUICK EDIT panel.

Use the following options to change a date range for a data block.

**Calendar**

 The Calendar allows you to create static or rolling dates using the following options:

- Date range field
- Calendar
- Preset drop-down menu
- Rolling date mode
- Customize expressions


**From cell**

The **[!UICONTROL From cell]** option allows you to reference dates entered in worksheet cells.

You have the option to exclude today on any selected date range.

 ![Report Builder Quick edit pane with calendar selected and Exclude today selected.](./assets/image17.png)

## Use the Calendar

When you use the **Calendar**, the date range field displays the current date range for the data block request. You can enter dates directly into the date range field or use a data range selection option.

### Date range field

To enter dates directly into the date range field

1. Click the date range field next to the calendar icon.

1. Enter start and end dates for your date range.

### Calendar

To select dates using the calendar

1. Click the calendar icon to display a monthly calendar.

1. Click a start date.

1. Click an end date.

To set a date range in reverse, click the end date first and then click the start date.

![Report Builder date range pane showing the calendar and the end date and the start date selected.](./assets/image18.png)

### Preset drop down menu

The preset drop-down menu includes a standard set of preset date ranges and date range components for a report suite that you saved or a report suite that was shared with you.

### Rolling dates

The rolling dates option allows you to select a date range using rolling dates.

1. Select **Use rolling dates**.

1. Select a rolling expression for your start and or end date.

    ![Report Builder date range pane showing Use rolling dates selected and the rolling expression.](./assets/image19.png)

    **Start of** — Allows you to select the beginning of a day, week, month, quarter, or year.

    **End of** — Allows you to select the end of a day, week, month, quarter, or year.

    **Fixed day** — Allows you to fix a start or end date while the other date is rolling.

1. Choose day, week, month, quarter, or year as the rolling period.

    ![Report Builder date range pane showing the current day selected.](./assets/image20.png)

1. Add or subtract days, weeks, months, quarters, or years from your rolling date.

    ![Report Builder date range pane showing the current day plus 14 days selected.](./assets/image21.png)

1. Click Next to define the data range.

    Use the date preview to confirm the resulting date range is the desired range.

### Custom expressions

The custom expression option allows you to change the date range by building a custom expression or you can enter an arithmetic formula.

1. Select **Use rolling dates**.

1. Select **Use custom expression**.

    When you select the **Use custom expression** option, the standard rolling date range controls are disabled.

    ![Select Use custom expression showing tm-1m to td-1d.](./assets/custom_expression.png)

1. Enter a custom expression.

    For a sample list of custom expressions, see **Date expressions**.

1. Use the date preview to verify the resulting date range is the desired range.

#### Create a custom expression

1. Enter a **Date reference**.

1. Add **Date operators** to move the date to the past or future.

You can enter a custom date expression that includes multiple operators, such as ```tm-11m-1d```.

#### Date references

The following table lists date reference examples.

| Date Reference | Type         | Description                |
|----------------|--------------|----------------------------|
| 1/1/10         | Static Date  | Entered in ISO Date format |
| td             | Rolling Date | Start of current day       |
| tw             | Rolling Date | Start of current week      |
| tm             | Rolling Date | Start of current month     |
| tq             | Rolling Date | Start of current quarter   |
| ty             | Rolling Date | Start of current year      |

#### Date operators

The following table lists date operator examples.

| Date Operators | Unit    | Description   |
|----------------|---------|--------------------|
| +6d            | Day     | Add 6 days to the Date Reference |
| +1w            | Week    | Add one full week to the Date Reference |
| -2m            | Month   | Subtract 2 full months to the Date Reference |
| -4q            | Quarter | Subtract 4 quarters to the Date Reference |
| -1y            | Year    | Subtract one year to the Date Reference |

#### Date expressions

The following table lists date expression examples.

| Date Expression | Meaning                              |
|-----------------|--------------------------------------|
| td-1w           | First day of last week               |
| tm-1d           | Last day of previous month           |
| td-52w          | Same day, 52 weeks ago               |
| tm-11m-1d       | Last day of the same month last year |
| "2020-09-06"    | Sept 9th, 2020                       |

## Date range from cell

The date range can be specified in worksheet cells. Use the **Date range from cell** option to choose the data block start and end date from selected cells. When you select the **From cell** option, the panel displays **From** and **To** fields where you can enter a cell location.

![Select From cell Sheet1!H4 to Sheet1!I4](./assets/image23.png)

## Exclude today

Choose the **Exclude today** option to exclude today from a selected date range. Choosing to include today may pull incomplete data for today.

When selected, the **Exclude today** option excludes the current day from all date range modes including calendar, rolling dates, or custom expressions.

## Valid date ranges

The following list describe valid date range formats.

- The start and end dates must be in the following format: YYYY-MM-DD

- The start date must be earlier to or equal to the end date. Both dates can be set to the future.

- When using rolling dates, the start date must be today or in the past. It must be in the past if **Exclude today** is checked.

- You can create a static date range set for the future. For example, you may need to set a future date for a marketing campaign launch next week. This option creates a workbook monitoring for a campaign ahead of time.

## Change the date range

You can edit the date range of an existing data block by selecting Edit data block in the COMMANDS panel or by selecting the date range link in the QUICK EDIT panel.

**Edit data block** — Allows you to edit multiple data block parameters, including date range, for a single data block.

**Quick Edit: Date range** — Allows you to edit the date range of one or more data blocks.

To edit the date range from the QUICK EDIT panel

1. Select cells within one or more data blocks in a worksheet.

1. Click the **Date range** link in the QUICK EDIT panel.

1. Select the date range using any of the date selection options.

1. Click **Apply**.


Report Builder applies the new date range to all data blocks in the selection.
-->