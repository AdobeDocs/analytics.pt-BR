---
description: Filtros de classificação e condicionais que você configura usando lógica booleana com expressões de pesquisa E/OU.
title: Filtragem mais popular
topic: Report builder
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtragem mais popular

Filtros de classificação e condicionais que você configura usando lógica booleana com expressões de pesquisa E/OU.

Os filtros mais populares são filtros expressões que você configura usando lógica booleana com condições E/OU, como [!UICONTROL Page does not contain]*`<product name>`* com condições ou grupos de condições como [!UICONTROL Includes All], [!UICONTROL Includes Any]ou [!UICONTROL Excludes All]. É possível [salvar](/help/analyze/report-builder/layout/c-filter-dimensions/saved-filters.md) essas expressões para outra solicitação nessa ou em outras pastas de trabalho.

**Para criar um filtro mais popular**

1. Crie ou edite uma solicitação e avance para o [!UICONTROL Request Wizard: Step 2].

   ![Informações da etapa](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.
1. No [!UICONTROL Choose Page] formulário, ative **[!UICONTROL Most Popular]** e configure as seguintes opções:

   **Classificação inicial:** A classificação inicial de uma dimensão. A classificação padrão de 1 indica o item no topo da lista de dados relatados. For example, for the dimension [!UICONTROL Page], a starting mark of 1 indicates the single most requested page of your site. Você poderia especificar 10 ou outro valor como a célula de classificação inicial, o que produz um relatório que começa com 10 como a mais alta. As métricas são organizadas em ordem decrescente, de modo que os itens de linha com maior atividade sejam relatados primeiro na lista. Se você precisar de mais de 50.000 nomes de páginas em uma solicitação, mas tiver milhares de páginas sobre as quais emitir relatórios, poderá copiar a solicitação e alterar a classificação inicial para recuperar os dados apropriados em blocos de 50.000.

   **Número de entradas:** ( [!UICONTROL Pivot Layout] somente) Define quantos itens são reportados para uma métrica específica em um intervalo de datas. Algumas métricas podem listar centenas de entradas, enquanto outras podem mostrar apenas algumas. For example, for the dimension [!UICONTROL Site Section], a number of entries of 25 indicates that the report shows the 25 most visited pages.

   Setas permitem alterar o [!UICONTROL Starting Rank] e [!UICONTROL Number of Entries] do primeiro ponto de dados na planilha. Por padrão, o [!UICONTROL Starting Rank] está definido como 1 e o [!UICONTROL Number of Entries] como 10. Esses valores são ajustáveis de um mínimo a um máximo de 50.000 para determinadas métricas. Cada métrica tem seu próprio teto [!UICONTROL Number of Entries]. Valores negativos ou zero não são permitidos nesses campos. If you choose a [!UICONTROL Starting Rank] as 15 and [!UICONTROL Number of Entries] as 10, data requests for the metric return the 10 most visited pages, where the first most visited page is number 15 in the list for the specific date range. Todas as páginas mais solicitadas classificadas de 15ª a 25ª são listadas em ordem decrescente.

   >[!NOTE]
   >
   >Aplicar filtros a solicitações existentes provoca alterações nos dados apresentados. Suponha que você mapeou os dez primeiros [!UICONTROL Pages] para as células $A$1 a $A$10, com 1 para [!UICONTROL Starting Rank] e 10 para [!UICONTROL Number of Entries]. If you change these values to show 1 for [!UICONTROL Starting Rank] and only 3 for [!UICONTROL Number of Entries], the data previously filling cells $A$4 through $A$10 will no longer appear.

1. To create a search expression, click **[!UICONTROL Add]**.

   ![Informações da etapa](assets/expressions_define_filter.png)

1. On the [!UICONTROL Define Filter] form, configure the conditions appropriate for your needs.

   ![select_cell_icon.png](assets/select_cell_icon.png): Permite localizar uma condição definida no valor de uma célula.

   **Adicionar condição:** Adiciona uma condição à expressão. Não há limite para o número de condições que podem ser adicionadas.

1. Clique em **[!UICONTROL OK]**.

   ![Informações da etapa](assets/choose_page_02.png)

1. No [!UICONTROL Choose Page] formulário, clique **[!UICONTROL Save]** para salvar a expressão.
1. Clique em **[!UICONTROL OK]**.
