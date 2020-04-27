---
description: Filtros que aplicam termos de dimensões específicos.
title: Filtros específicos
topic: Report builder
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtros específicos

Filtros que aplicam termos de dimensões específicos.

Você pode pesquisar por itens de dimensão específicos criando um filtro que corresponda a critérios exatos. Por exemplo, você pode criar o seguinte tipo de filtro: página em [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Para criar um filtro Específico**

1. Crie ou edite uma solicitação e avance para o [!UICONTROL Request Wizard: Step 2].

   ![Resultado da etapa](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.

   ![Resultado da etapa](assets/choose_page_specific01.png)

1. Enable **[!UICONTROL Specific]**, then enable one of the following options:

   * **A partir de um intervalo de células:** Permite selecionar dados a partir de células. Você pode selecionar:
   * **Todas as células do intervalo:** Permite mapear cada célula para o intervalo. Texto descritivo explica quantos grupos de células precisam ser selecionados. Para mapear mais de um grupo de células, pressione a tecla Ctrl à medida que faz seleções sucessivas. Se o intervalo a ser mapeado contiver somente uma célula, essa será a única opção disponível
   * **Primeira célula do intervalo:** Você precisa somente selecionar a célula superior esquerda do intervalo e, em seguida, escolher uma direção para os dados. Além disso, se a solicitação tiver vários períodos, você escolhe a direção dos períodos e se deseja pular um número definido de células entre os períodos.
   * **A partir da lista:** Permite selecionar dados de uma lista à qual você pode adicionar dados.
1. If you enable **[!UICONTROL From List]**, select any available listed items or click **[!UICONTROL Add]**.

   When you click **[!UICONTROL Add]**, the [!UICONTROL Select From List] form displays a list of available dimension values for the current request date range, limited to the first 10,000 items. You can search across these items or click **[!UICONTROL More ...]**, which displays the [!UICONTROL Search Form], so that you can create a more detailed search for dimensions.
1. No [!UICONTROL Select From List], clique em **[!UICONTROL OK]**.
1. On the [!UICONTROL Choose Page] form, save your Specific filter if you want, then click **[!UICONTROL OK]**.
