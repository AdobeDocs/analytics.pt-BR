---
description: Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.
seo-description: Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.
seo-title: Relatório do [!DNL Activity Map] no Analytics
solution: Analytics
title: Relatório do [!DNL Activity Map] no Analytics
topic: Activity Map
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# [!DNL Activity Map] relatórios no Analytics

Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.

## Set permissions {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Before users can report on [!DNL Activity Map] dimensions, you as the Admin need to

* [Adicione usuários ao Grupo](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)de Acesso do [!DNL Activity Map].
* Adicionar conjuntos de relatórios que você deseja que tenham acesso a este grupo. Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL [!DNL Activity Map]Access]** &gt; **[!UICONTROL Edit]**.
* Personalizar o acesso de usuários a dimensões. Consulte a seção abaixo.

## Dimensões do Analytics [!DNL Activity Map]{#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Você pode [personalizar o acesso dos usuários a dimensões](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html) em nível granular. Here are the [!DNL Activity Map] dimensions available in Analytics:

| Dimensão | Descrição |
|---|---|
| [!DNL Activity Map] Página | Lista as páginas nas quais um link foi clicado. |
| [!DNL Activity Map] Região | Lista todas as regiões de links coletados em todo o site. Observe que, se uma região for exibida em várias páginas, a métrica será agregada em todas as páginas. |
| [!DNL Activity Map] Links | Lista todos os links coletados em todo o site. |
| [!DNL Activity Map] Links e região | Lista todos os links coletados, que contenham região, em todo o site. |
| [!DNL Activity Map] XY | Não usado |

* Essas dimensões devem estar disponíveis na Analysis Workspace, em Reports &amp; Analytics e no Report Builder, desde que a implementação do Analytics esteja [enabled for [!DNL Activity Map]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* In Reports &amp; Analytics, navigate to **[!UICONTROL View All Reports]** &gt; **[!UICONTROL [!DNL Activity Map]]**.

* To look at a link and region for a specific page, all you need to do is create a breakdown from the desired [!DNL Activity Map] page into the [!DNL Activity Map] Links &amp; Region.

