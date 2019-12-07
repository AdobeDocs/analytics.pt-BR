---
description: Etapas administrativas para configurar relatórios em tempo real.
title: Configuração de relatórios em tempo real
topic: Admin tools
uuid: f48692a0-77c0-4ee4-b3ec-eaa842d06ac8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Configuração de relatórios em tempo real

Etapas administrativas para configurar relatórios em tempo real.

Configurar relatórios em tempo real dentro de Reports &amp; Analytics consiste em selecionar o conjunto de relatórios e configurar até três relatórios para ele.

1. Selecione o conjunto de relatórios para o qual você deseja ativar os relatórios em tempo real.

   Navegue até **[!UICONTROL Analytics]**&gt;**[!UICONTROL Relatórios]** &gt; **[!UICONTROL Exibir todos os relatórios &gt; Métricas do site]** &gt; **[!UICONTROL Tempo real]** e selecione o conjunto de relatórios do menu suspenso no início da página:

   ![](assets/report_suite_selector.png)

   Se você tentar exibir relatórios em tempo real para um conjunto de relatórios não configurado para relatórios em tempo real, uma mensagem exibe que você configurou o conjunto de relatórios.

   ![](assets/rep_suite_not_set_up.png)

1. Clique em **[!UICONTROL Configurar]** (ícone de engrenagem) para executar o [!UICONTROL Gerenciador de conjunto de relatórios].

   (Também disponível em **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador &gt; Conjuntos de relatórios]** &gt; **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Tempo real]**.)

1. Ative a configuração **[!UICONTROL Ativar tempo real]**.
1. Configure a coleção de dados em tempo real para até três relatórios, com uma métrica e três dimensões ou classificações por relatório.

   ![](assets/real_time_admin.png)

   Para obter informações sobre métricas e dimensões em tempo real compatíveis, consulte [Métricas e dimensões compatíveis](/help/admin/admin/realtime/realtime-metrics.md).

   Caso tenha criado classificações, elas serão exibidas recuadas abaixo da dimensão para a qual foram definidas:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >No momento, não oferecemos suporte para habilitar dimensões duplicadas para um relatório em tempo real, mesmo que uma classificação diferente seja selecionada para cada dimensão.

   Para obter mais informações sobre classificações, consulte [Sobre classificações](/help/components/c-classifications2/c-classifications.md).

   >[!NOTE]
   >
   >Algumas dimensões, como "Palavra-chave de pesquisa" ou "Produto", não persistem em tempo real como persistiriam em outro ponto do Adobe Analytics. Quando selecionar uma métrica não persistente, este aviso será exibido:

   ![](assets/warning_dimensions.png)

1. Clique em **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar e exibir relatório]**.

   Após essa configuração inicial de relatório, pode levar até 20 minutos para que o streaming de dados tenha início. A partir de então, os dados estarão imediatamente disponíveis. Para saber mais sobre a exibição de relatórios em tempo real, consulte [Executar um Relatório em tempo real](https://marketing.adobe.com/resources/help/en_US/sc/user/reports_realtime.html).

1. Por padrão, todos os usuários possuem acesso aos Relatórios em tempo real.
