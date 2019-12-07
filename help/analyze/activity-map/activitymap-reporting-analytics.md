---
description: Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.
title: Relatórios do Activity Map no Analytics
topic: Activity map
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Relatórios do Activity Map no Analytics

Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.

## Definir permissões {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Para que os usuários possam gerar relatórios sobre dimensões do Activity Map, como Administrador, você precisa

* [Adicionar usuários ao grupo de acesso do Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Adicionar conjuntos de relatórios que você deseja que tenham acesso a este grupo. Navegue até **[!UICONTROL Admin]** &gt; **[!UICONTROL Gerenciamento de usuários]** &gt; **[!UICONTROL Grupos]** &gt; **[!UICONTROL Acesso ao Activity Map]** &gt; **[!UICONTROL Editar]**.
* Personalizar o acesso de usuários a dimensões. Consulte a seção abaixo.

## Dimensões do Activity Map no Analytics {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Você pode [personalizar o acesso dos usuários a dimensões](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html) em nível granular. Veja a seguir as dimensões do Activity Map disponíveis no Analytics:

| Dimensão | Descrição |
|---|---|
| Página do Activity Map | Lista as páginas nas quais um link foi clicado. |
| Região do Activity Map | Lista todas as regiões de links coletados em todo o site. Observe que, se uma região for exibida em várias páginas, a métrica será agregada em todas as páginas. |
| Links do Activity Map | Lista todos os links coletados em todo o site. |
| Links e região do Activity Map | Lista todos os links coletados, que contenham região, em todo o site. |
| Activity Map XY | Não usado |

* Essas dimensões devem estar disponíveis na Analysis Workspace, em Reports &amp; Analytics e no Report Builder, desde que a implementação do Analytics esteja [habilitado para o Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Em Reports &amp; Analytics, navegue até **[!UICONTROL Exibir todos os relatórios]** &gt; **[!UICONTROL Activity Map]**.

* Para visualizar um link e uma região de uma página específica, tudo o que você precisa fazer é criar um relatório de decomposição da página desejada do Activity Map em Links e região do Activity Map.

