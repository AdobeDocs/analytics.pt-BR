---
description: Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.
title: Relatórios do Activity Map no Analytics
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 92%

---

# Relatórios do Activity Map no Analytics

Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.

## Definir permissões {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Para que os usuários possam gerar relatórios sobre dimensões do Activity Map, como Administrador, você precisa

* [Adicionar usuários ao grupo de acesso do Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Adicionar conjuntos de relatórios que você deseja que tenham acesso a este grupo. Navegue até **[!UICONTROL Admin]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Gerenciamento de usuários]** > **[!UICONTROL Grupos]** > **[!UICONTROL Acesso ao Activity Map]** > **[!UICONTROL Editar]**.
* Personalizar o acesso de usuários a dimensões. Consulte a seção abaixo.

## Dimensões do Activity Map no Analytics {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Você pode [personalizar o acesso dos usuários a dimensões](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) em nível granular. Veja a seguir as dimensões do Activity Map disponíveis no Analytics:

| Dimensão | Descrição |
|---|---|
| Página do Activity Map | Lista as páginas nas quais um link foi clicado. |
| Região do Activity Map | Lista todas as regiões de links coletados em todo o site. Observe que, se uma região for exibida em várias páginas, a métrica será agregada em todas as páginas. |
| Links do Activity Map | Lista todos os links coletados em todo o site. |
| Links e região do Activity Map | Lista todos os links coletados com sua região em todo o site. |
| Activity Map XY | Não usado |

* Essas dimensões devem estar disponíveis na Analysis Workspace, em Reports &amp; Analytics e no Report Builder, desde que a implementação do Analytics esteja [habilitado para o Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Em Reports &amp; Analytics, navegue até **[!UICONTROL Exibir todos os relatórios]** > **[!UICONTROL Activity Map]**.

* Para visualizar um link e uma região de uma página específica, tudo o que você precisa fazer é criar um relatório de decomposição da página desejada do Activity Map em Links e região do Activity Map.
