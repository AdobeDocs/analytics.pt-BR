---
description: Etapas administrativas para configurar relatórios em tempo real.
title: Configuração de relatórios em tempo real
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
TQID: https://experienceleague.adobe.com/HTu1UvUUIGK0SzAQWEFBclV-P1JaPCJUp6j5MiYC3A0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 68%

---

# Configuração de relatórios em tempo real

Etapas administrativas para configurar relatórios em tempo real.

Configurar relatórios em tempo real no Adobe Analytics consiste em selecionar o conjunto de relatórios e configurar até três relatórios para ele. Por padrão, todos os usuários possuem acesso aos Relatórios em tempo real.

1. Selecione o conjunto de relatórios para o qual você deseja habilitar os relatórios em tempo real.

   Navegue até **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Conjuntos de relatórios]**.

1. Clique em **[!UICONTROL Editar Configurações]** > **[!UICONTROL Tempo Real]**.

1. Configure a coleção de dados em tempo real para até três relatórios, com uma métrica e três dimensões ou classificações por relatório.

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/real_time_admin.png)

   Para obter informações sobre métricas e dimensões em tempo real compatíveis, consulte [Métricas e dimensões compatíveis](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md).

   Caso tenha criado classificações, elas serão exibidas recuadas abaixo da dimensão para a qual foram definidas:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >No momento, não oferecemos suporte para habilitar dimensões duplicadas para um relatório em tempo real, mesmo que uma classificação diferente seja selecionada para cada dimensão.

   >[!NOTE]
   >
   >Algumas dimensões, como &quot;Palavra-chave de pesquisa&quot; ou &quot;Produto&quot;, não persistem em tempo real como persistiriam em outro ponto do Adobe Analytics. Quando selecionar uma métrica não persistente, este aviso será exibido:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. Clique em **[!UICONTROL Salvar]**.

   Após essa configuração inicial do relatório, pode levar até 20 minutos para que os dados comecem a transmitir. A partir de então, os dados ficam imediatamente disponíveis.

1. Para exibir o relatório em tempo real, navegue até:

   **[!UICONTROL Workspace]** > **[!UICONTROL Relatórios]** > **[!UICONTROL Envolvimento]** > **[!UICONTROL Tempo Real]**.

