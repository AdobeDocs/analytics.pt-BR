---
description: Etapas administrativas para configurar relatórios em tempo real.
title: Configurar relatórios em tempo real
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
source-git-commit: ee55349a8c676023a5ce33b56592cad7642199b8
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 78%

---

# Configurar relatórios em tempo real

As informações a seguir contêm etapas administrativas para configurar relatórios em tempo real.

Isso consiste em selecionar o conjunto de relatórios e configurar até três relatórios para ele.

1. Selecione o conjunto de relatórios para o qual você deseja ativar os relatórios em tempo real.

   1. No Analysis Workspace, selecione a guia [!UICONTROL **Workspace**] e selecione [!UICONTROL **Relatórios**] > [!UICONTROL **Envolvimento**] > **[!UICONTROL Tempo real]**.

   1. Selecione o conjunto de relatórios no menu suspenso na parte superior:

      ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/report_suite_selector.png)

      Se você tentar exibir relatórios em tempo real para um conjunto de relatórios não configurado para relatórios em tempo real, uma mensagem exibe que você configurou o conjunto de relatórios.

      ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/rep_suite_not_set_up.png)

1. Selecione **[!UICONTROL Configurar]** para executar o [!UICONTROL Gerenciador de Conjunto de Relatórios].

   (Também disponível em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador > Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Tempo real]**.)

1. Ative a configuração **[!UICONTROL Ativar tempo real]**.
1. Configure a coleção de dados em tempo real para até três relatórios, com uma métrica e três dimensões ou classificações por relatório.

   ![](assets/real_time_admin.png)

   Para obter informações sobre métricas e dimensões em tempo real compatíveis, consulte [Métricas e dimensões compatíveis](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   Caso tenha criado classificações, elas serão exibidas recuadas abaixo da dimensão para a qual foram definidas:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >No momento, não oferecemos suporte para habilitar dimensões duplicadas para um relatório em tempo real, mesmo que uma classificação diferente seja selecionada para cada dimensão.

   Para obter mais informações sobre classificações, consulte [Sobre classificações](/help/components/classifications/c-classifications.md).

   >[!NOTE]
   >
   >Algumas dimensões, como &quot;Palavra-chave de pesquisa&quot; ou &quot;Produto&quot;, não persistem em tempo real como persistiriam em outro ponto do Adobe Analytics. Quando selecionar uma métrica não persistente, este aviso será exibido:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Selecione **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar e exibir relatório]**.

   Após essa configuração inicial de relatório, pode levar até 20 minutos para que o streaming de dados tenha início. A partir de então, os dados estarão imediatamente disponíveis. Para saber mais sobre a exibição de relatórios em tempo real, consulte [Executar um Relatório em tempo real](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/t-running-report-types.html?lang=pt-BR).

1. Por padrão, todos os usuários possuem acesso aos Relatórios em tempo real.
