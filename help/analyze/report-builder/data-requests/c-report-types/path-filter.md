---
description: Descreve as etapas envolvidas na aplicação de filtros para um relatório de definição de caminho.
title: Filtrar relatório de caminho com o Assistente de solicitação
topic: Report builder
uuid: 9b22d5b5-7ae8-49a2-90ae-0c1075562bbe
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtrar relatório de caminho com o Assistente de solicitação

Descreve as etapas envolvidas na aplicação de filtros para um relatório de definição de caminho.

Esse exemplo usa Caminhos de seção do site.

1. No Report Builder da Adobe, clique em **[!UICONTROL Criar]** para abrir o Assistente de solicitação.
1. Selecione o conjunto de relatórios apropriado.
1. Na visualização de árvore, selecione **[!UICONTROL Caminhos]** > **[!UICONTROL Seções do site]** > **[!UICONTROL Caminhos de seção do site]**.

   ![](assets/site_section_path_1.png)

1. Especifique as datas apropriadas.
1. Clique em **[!UICONTROL Próximo]**.
1. Na Etapa 2 do Assistente, em **[!UICONTROL Etiquetas de linha]**, clique no link **[!UICONTROL 1-10 principais (padrão aplicado)]**. Em um relatório de caminho, um padrão é aplicado por padrão.

   ![](assets/site_section_path_2.png)

1. Selecione a opção **[!UICONTROL Filtrar]**.

   ![](assets/filter_option.png)

1. Na caixa de diálogo **[!UICONTROL Definir padrão de caminho &#39;Caminhos de seção do site&#39;]**, você pode especificar
   1. a classificação inicial do primeiro relatório.
   1. o número de entradas que você deseja exibir neste relatório.
1. Clique em **[!UICONTROL Editar]** para definir um padrão de caminho.
1. Se você deseja um padrão personalizado, arraste e solte quaisquer **[!UICONTROL Objetos de padrão]** da lista à esquerda na **[!UICONTROL Tela de construção de padrão]** à direta.

   ![](assets/custom_pattern.png)

1. Você também pode selecionar um padrão predefinido da lista suspensa **[!UICONTROL Selecionar um padrão]** e modificá-lo. Estes são os padrões disponíveis:

   ![](assets/select_a_pattern.png)

   Alguns desses padrões são específicos do Report Builder: Padrão de próximo item do Caminho de entrada, Padrão de próximo item do Caminho de saída, Padrão do próximo item.
1. Para editar um padrão predefinido,
   1. Selecione-o. Por exemplo, selecione o **[!UICONTROL Padrão de saída de site]**: ![](assets/exited_site_pattern.png)

   1. Agora você deve definir o caminho de seção do site que o usuário segue antes de sair. Clique em **[!UICONTROL Itens específicos: 0 selecionados]**. Você pode definir esse caminho ao selecionar entre várias células (se você está editando uma solicitação existente) ou ao selecionar a partir de uma lista de seções.
   1. Para selecionar de várias células de uma solicitação anterior, selecione **[!UICONTROL De várias células]** e clique no ícone seletor de células. Em seguida, escolha as células no relatório. ![](assets/choose_site_section_paths.png)

   1. Para selecionar de uma lista com seções do site, selecione **[!UICONTROL Da lista]** e clique em **[!UICONTROL Adicionar]**.
   1. Mova elementos da coluna **[!UICONTROL Elementos disponíveis]** para a coluna **[!UICONTROL Elementos selecionados]** ao selecioná-los e clicando na seta laranja. Clique em **[!UICONTROL OK]**. ![](assets/move_site_section_elements.png)

   1. Para salvar o padrão estabelecido, clique em **[!UICONTROL Salvar]**.
   1. Clique em **[!UICONTROL OK]** três vezes e, em seguida, clique em **[!UICONTROL Concluir]**. A solicitação de caminho filtrada é gerada.
