---
description: Etapas administrativas para configurar relatórios em tempo real.
seo-description: Etapas administrativas para configurar relatórios em tempo real.
seo-title: Configuração de relatórios em tempo real
solution: Analytics
title: Configuração de relatórios em tempo real
topic: Ferramentas administrativas
uuid: f48692a0-77c0-4ee4-b3ec-eaa842d06ac8
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Configuração de relatórios em tempo real

Etapas administrativas para configurar relatórios em tempo real.

Configurar relatórios em tempo real dentro de Reports &amp; Analytics consiste em selecionar o conjunto de relatórios e configurar até três relatórios para ele.

1. Selecione o conjunto de relatórios para o qual você deseja ativar os relatórios em tempo real.

   Navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** &gt; **[!UICONTROL View All Reports &gt; Site Metrics]** &gt; **[!UICONTROL Real-Time]** and select the report suite from the drop-down at the top:

   ![](assets/report_suite_selector.png)

   Se você tentar exibir relatórios em tempo real para um conjunto de relatórios não configurado para relatórios em tempo real, uma mensagem exibe que você configurou o conjunto de relatórios.

   ![](assets/rep_suite_not_set_up.png)

1. Click **[!UICONTROL Configure]** (gear icon) to run the [!UICONTROL Report Suite Manager].

   (Also available under **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Real-Time]**.)

1. Turn on the **[!UICONTROL Enable Real-Time]** setting.
1. Configure a coleção de dados em tempo real para até três relatórios, com uma métrica e três dimensões ou classificações por relatório.

   ![](assets/real_time_admin.png)

   Para obter informações sobre métricas e dimensões em tempo real suportadas, consulte Métricas e dimensões [suportadas](/help/admin/admin/realtime/realtime-metrics.md).

   Caso tenha criado classificações, elas serão exibidas recuadas abaixo da dimensão para a qual foram definidas:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >Para um único relatório em tempo real, não oferecemos suporte à ativação de dimensões duplicadas, mesmo se uma classificação diferente for selecionada para cada dimensão.

   Para obter mais informações sobre classificações, consulte [Sobre classificações](/help/components/c-classifications2/c-classifications.md).

   >[!NOTE]
   >
   >Algumas dimensões, como "Palavra-chave de pesquisa" ou "Produto", não persistem em tempo real como em qualquer outro lugar no Adobe Analytics. Quando selecionar uma métrica não persistente, este aviso será exibido:

   ![](assets/warning_dimensions.png)

1. Click **[!UICONTROL Save]** or **[!UICONTROL Save and View Report]**.

   Após essa configuração inicial de relatório, pode levar até 20 minutos para que o streaming de dados tenha início. A partir de então, os dados estarão imediatamente disponíveis. Para saber mais sobre a exibição de relatórios em tempo real, consulte [Executar um Relatório em tempo real](https://marketing.adobe.com/resources/help/en_US/sc/user/reports_realtime.html).

1. Por padrão, todos os usuários possuem acesso aos Relatórios em tempo real.
