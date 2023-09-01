---
description: Descreve as etapas envolvidas na aplicação de filtros para um relatório de definição de caminho.
title: Filtrar relatório de caminho com o Assistente de solicitação
feature: Report Builder
role: User, Admin
exl-id: 085351b3-4d9c-45cf-b2a8-379f05932b26
source-git-commit: d218d07ec16e981d7e148092b91fbbd5711e840f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 63%

---

# Filtrar relatório de caminho com o Assistente de solicitação

Descreve as etapas envolvidas na aplicação de filtros para um relatório de definição de caminho.

Esse exemplo usa Caminhos de seção do site.

1. No Report Builder da Adobe, clique em **[!UICONTROL Criar]** para abrir o Assistente de solicitação.
1. Selecione o conjunto de relatórios apropriado.
1. Na visualização de árvore, selecione **[!UICONTROL Caminhos]** > **[!UICONTROL Seções do site]** > **[!UICONTROL Caminhos de seção do site]**.

   ![Captura de tela mostrando os Caminhos de seção do site selecionados.](assets/site_section_path_1.png)

1. Especifique as datas apropriadas.

1. Clique em **[!UICONTROL Próximo]**.

1. Na Etapa 2 do Assistente, em **[!UICONTROL Etiquetas de linha]**, clique no link **[!UICONTROL 1-10 principais (padrão aplicado)]**. Em um relatório de caminho, um padrão é aplicado por padrão.

   ![Captura de tela mostrando o padrão de caminho padrão.](assets/site_section_path_2.png)

1. Selecione a opção **[!UICONTROL Filtrar]**.

   ![Captura de tela destacando a opção Filtrar.](assets/filter_option.png)

1. Na caixa de diálogo **[!UICONTROL Definir padrão de caminho &#39;Caminhos de seção do site&#39;]**, você pode especificar
   * A classificação inicial do primeiro relatório.
   * O número de entradas que você deseja exibir neste relatório.
1. Clique em **[!UICONTROL Editar]** para definir um padrão de caminho.

1. Se você deseja um padrão personalizado, arraste e solte quaisquer **[!UICONTROL Objetos de padrão]** da lista à esquerda na **[!UICONTROL Tela de construção de padrão]** à direta.

   ![](assets/custom_pattern.png)

1. Você também pode selecionar um padrão predefinido da lista suspensa **[!UICONTROL Selecionar um padrão]** e modificá-lo. Estes são os padrões disponíveis:

   ![](assets/select_a_pattern.png)

   Alguns desses padrões são específicos do Report Builder: Padrão do Próximo Item do Caminho de Entrada, Padrão do Próximo Item do Caminho de Saída, Padrão do Próximo Item.

## Para editar um padrão predefinido

É possível editar um padrão predefinido depois de selecionar um padrão.

1. Continuando nas etapas acima, selecione o padrão. Por exemplo, selecione o **[!UICONTROL Padrão de saída de site]**:

   ![Captura de tela destacando o padrão selecionado.](assets/exited_site_pattern.png)

1. Defina o caminho de seção do site que o usuário segue antes de sair. Clique em **[!UICONTROL Itens específicos: 0 selecionados]**. Você pode definir esse caminho ao selecionar entre várias células se estiver editando uma solicitação existente, ou ao selecionar a partir de uma lista de seções.

1. Para selecionar de várias células de uma solicitação anterior, selecione **[!UICONTROL De várias células]** e clique no ícone seletor de células. Em seguida, escolha as células no relatório.

   ![Captura de tela mostrando as opções para escolher De várias células ou de uma lista.](assets/choose_site_section_paths.png)

1. Para selecionar de uma lista com seções do site, selecione **[!UICONTROL Da lista]** e clique em **[!UICONTROL Adicionar]**.

1. Mova elementos da coluna **[!UICONTROL Elementos disponíveis]** para a coluna **[!UICONTROL Elementos selecionados]** ao selecioná-los e clicando na seta laranja. Clique em **[!UICONTROL OK]**.

   ![Captura de tela mostrando os Elementos disponíveis e os Elementos selecionados.](assets/move_site_section_elements.png)

1. Para salvar o padrão estabelecido, clique em **[!UICONTROL Salvar]**.

1. Clique em **[!UICONTROL OK]** três vezes e clique em **[!UICONTROL Concluir]** para gerar o caminho filtrado.
