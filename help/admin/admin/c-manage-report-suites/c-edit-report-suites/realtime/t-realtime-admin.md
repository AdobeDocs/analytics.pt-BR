---
description: Etapas administrativas para configurar relatórios em tempo real.
title: Configuração de relatórios em tempo real
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 76%

---

# Configuração de relatórios em tempo real

Etapas administrativas para configurar relatórios em tempo real.

Configurar relatórios em tempo real no Adobe Analytics consiste em selecionar o conjunto de relatórios e configurar até três relatórios para ele. Por padrão, todos os usuários possuem acesso aos Relatórios em tempo real.

1. Selecione o conjunto de relatórios para o qual você deseja ativar os relatórios em tempo real.

   Navegue até **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Conjuntos de relatórios]**.

1. Clique em **[!UICONTROL Editar Configurações]** > **[!UICONTROL Tempo Real]**.

1. Configure a coleção de dados em tempo real para até três relatórios, com uma métrica e três dimensões ou classificações por relatório.

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/real_time_admin.png)

   Para obter informações sobre métricas e dimensões em tempo real compatíveis, consulte [Métricas e dimensões compatíveis](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   Caso tenha criado classificações, elas serão exibidas recuadas abaixo da dimensão para a qual foram definidas:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >No momento, não oferecemos suporte para habilitar dimensões duplicadas para um relatório em tempo real, mesmo que uma classificação diferente seja selecionada para cada dimensão.

   >[!NOTE]
   >
   >Algumas dimensões, como &quot;Palavra-chave de pesquisa&quot; ou &quot;Produto&quot;, não persistem em tempo real como persistiriam em outro ponto do Adobe Analytics. Quando selecionar uma métrica não persistente, este aviso será exibido:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Clique em **[!UICONTROL Salvar]**.

   Após essa configuração inicial de relatório, pode levar até 20 minutos para que o streaming de dados tenha início. A partir de então, os dados ficam imediatamente disponíveis.

1. Para exibir o relatório em tempo real, navegue até:

   **[!UICONTROL Workspace]** > **[!UICONTROL Relatórios]** > **[!UICONTROL Envolvimento]** > **[!UICONTROL Tempo Real]**.

