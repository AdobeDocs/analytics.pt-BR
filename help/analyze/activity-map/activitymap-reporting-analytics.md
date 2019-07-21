---
description: Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.
seo-description: Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.
seo-title: Relatórios do Activity Map no Analytics
solution: Analytics
title: Relatórios do Activity Map no Analytics
topic: Activity Map
uuid: 057 c 6 ab 2-aa 06-4779-ac 16-f 9 b 367 d 9 ea 43
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Relatórios do Activity Map no Analytics

Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.

## Set permissions {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Para que os usuários possam gerar relatórios sobre dimensões do Activity Map, como Administrador, você precisa

* [Adicionar usuários ao grupo de acesso do Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Adicionar conjuntos de relatórios que você deseja que tenham acesso a este grupo. Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL Activity Map Access]** &gt; **[!UICONTROL Edit]**.
* Personalizar o acesso de usuários a dimensões. Consulte a seção abaixo.

## Analytics Activity Map dimensions {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Você pode [personalizar o acesso dos usuários a dimensões](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html) em nível granular. Veja a seguir as dimensões do Activity Map disponíveis no Analytics:

| Dimensão | Descrição |
|---|---|
| Página do Activity Map | Lista as páginas nas quais um link foi clicado. |
| Região do Activity Map | Lista todas as regiões de links coletados em todo o site. Observe que, se uma região for exibida em várias páginas, a métrica será agregada em todas as páginas. |
| Links do Activity Map | Lista todos os links coletados em todo o site. |
| Links e região do Activity Map | Lista todos os links coletados, que contenham região, em todo o site. |
| Activity Map XY | Não usado |

* Essas dimensões devem estar disponíveis na Analysis Workspace, em Reports &amp; Analytics e no Report Builder, desde que a implementação do Analytics esteja [habilitado para o Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* In Reports &amp; Analytics, navigate to **[!UICONTROL View All Reports]** &gt; **[!UICONTROL Activity Map]**.

* Para visualizar um link e uma região de uma página específica, tudo o que você precisa fazer é criar um relatório de decomposição da página desejada do Activity Map em Links e região do Activity Map.

