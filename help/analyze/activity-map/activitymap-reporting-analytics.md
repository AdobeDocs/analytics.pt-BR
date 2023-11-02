---
description: Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.
title: Relatórios do Activity Map no Analytics
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: 4af73d19afd8844f814aafd45153cc638aa535d6
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 92%

---

# Relatórios do Activity Map no Analytics

Descreve como definir permissões e quais dimensões estão disponíveis no Analytics.

## Definir permissões {#permissions}

Para que os usuários possam gerar relatórios sobre dimensões do Activity Map, como Administrador, você precisa

* [Adicionar usuários ao perfil de produto Acesso ao Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* Personalizar o acesso de usuários a dimensões. Consulte a seção abaixo.

## Dimensões do Activity Map no Analytics {#dimensions}

Você pode [personalizar o acesso dos usuários a dimensões](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) em nível granular. Veja a seguir as dimensões do Activity Map disponíveis no Analytics:

| Dimensão | Descrição |
|---|---|
| Página do Activity Map | Lista as páginas nas quais um link foi clicado. |
| Região do Activity Map | Lista todas as regiões de links coletados em todo o site. Observe que, se uma região for exibida em várias páginas, a métrica será agregada em todas as páginas. |
| Links do Activity Map | Lista todos os links coletados em todo o site. |
| Links e região do Activity Map | Lista todos os links coletados com sua região em todo o site. |
| Activity Map XY | Não usado |

* Essas dimensões devem estar disponíveis na Analysis Workspace, em Reports &amp; Analytics e no Report Builder, desde que a implementação do Analytics esteja [habilitado para o Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* Em Reports &amp; Analytics, navegue até **[!UICONTROL Exibir todos os relatórios]** > **[!UICONTROL Activity Map]**.
* Para visualizar um link e uma região de uma página específica, tudo o que você precisa fazer é criar um relatório de decomposição da página desejada do Activity Map em Links e região do Activity Map.
