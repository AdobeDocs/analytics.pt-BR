---
description: Descreve as etapas envolvidas na aplicação de filtros para um relatório de definição de caminho.
title: Filtrar relatório de caminho com o Assistente de solicitação
topic: Report builder
uuid: 9b22d5b5-7ae8-49a2-90ae-0c1075562bbe
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtrar relatório de caminho com o Assistente de solicitação

Descreve as etapas envolvidas na aplicação de filtros para um relatório de definição de caminho.

Esse exemplo usa Caminhos de seção do site.

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. Selecione o conjunto de relatórios apropriado.
1. Na visualização em árvore à esquerda, selecione **[!UICONTROL Paths]** > **[!UICONTROL Site Sections]** > **[!UICONTROL Site Section Paths]**.

   ![](assets/site_section_path_1.png)

1. Especifique as datas apropriadas.
1. Clique em **[!UICONTROL Next]**.
1. Na Etapa 2 do Assistente, em **[!UICONTROL Row Labels]**, clique no **[!UICONTROL Top 1-10 (pattern applied)]** link. Em um relatório de caminho, um padrão é aplicado por padrão.

   ![](assets/site_section_path_2.png)

1. Selecione a opção **[!UICONTROL Filter]**.

   ![](assets/filter_option.png)

1. Na **[!UICONTROL Define 'Site Section Paths' Path Pattern]** caixa de diálogo, você pode especificar
   1. a classificação inicial do primeiro relatório.
   1. o número de entradas que você deseja exibir neste relatório.
1. Click **[!UICONTROL Edit]** to define a path pattern.
1. If you want a custom pattern, drag and drop any **[!UICONTROL Pattern Objects]** from the list on the left into the **[!UICONTROL Pattern Build Canvas]** on the right.

   ![](assets/custom_pattern.png)

1. You can also select a predefined pattern from the **[!UICONTROL Select a Pattern]** drop-down list and modify it. Estes são os padrões disponíveis:

   ![](assets/select_a_pattern.png)

   Alguns desses padrões são específicos do Report Builder: Padrão de próximo item do Caminho de entrada, Padrão de próximo item do Caminho de saída, Padrão do próximo item.
1. Para editar um padrão predefinido,
   1. Selecione-o. Por exemplo, selecione o **[!UICONTROL Exited Site Pattern]**: ![](assets/exited_site_pattern.png)

   1. Agora você deve definir o caminho de seção do site que o usuário segue antes de sair. Clique em **[!UICONTROL Specific Item(s): 0 selected]**. Você pode definir esse caminho ao selecionar entre várias células (se você está editando uma solicitação existente) ou ao selecionar a partir de uma lista de seções.
   1. To select from a range of cells from a previous request, select **[!UICONTROL From range of cells]** and click the cell selector icon. Em seguida, escolha as células no relatório. ![](assets/choose_site_section_paths.png)

   1. To select from a list of site sections, select **[!UICONTROL From list]** and click **[!UICONTROL Add]**.
   1. Move elements from the **[!UICONTROL Available Elements]** column to the **[!UICONTROL Selected Elements]** column by selecting them and clicking the orange arrow. Clique em **[!UICONTROL OK]**. ![](assets/move_site_section_elements.png)

   1. To save the pattern you just established, click **[!UICONTROL Save]**.
   1. Click **[!UICONTROL OK]** three times and then click **[!UICONTROL Finish]**. A solicitação de caminho filtrada é gerada.
