---
title: Implementar o Adobe Analytics com a Adobe Experience Platform Edge
description: Visão geral do uso de dados XDM da Experience Platform no Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9d9212313f54e4b44c5341754942ac0e0c78b84c
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 35%

---

# Implementar o Adobe Analytics com a Adobe Experience Platform Edge

A Adobe Experience Platform Edge permite enviar dados destinados a vários produtos para um local centralizado. A Experience Edge encaminha as informações apropriadas para os produtos desejados. Esse conceito permite consolidar os esforços de implementação, especialmente abrangendo várias soluções de dados.

A Adobe oferece três principais maneiras de enviar dados para a Experience Edge:

* **[SDK da Web da Adobe Experience Platform](web-sdk/overview.md)**: usar a extensão de SDK da Web da coleção de dados da Adobe Experience Platform para enviar dados para o Edge.
* **[SDK móvel da Adobe Experience Platform](mobile-sdk/overview.md)**: usar a extensão de SDK móvel da coleção de dados da Adobe Experience Platform para enviar dados para o Edge.
* **[API do servidor de rede de borda da Adobe Experience Platform](server-api/overview.md)**: envie dados diretamente para o Edge usando uma API.



## Como a Adobe Analytics lida com dados da Experience Edge

O envio de dados para o Experience Edge deve estar em conformidade com esquemas com base em [XDM (Experience Data Model, modelo de dados de experiência)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR). O XDM oferece flexibilidade em quais campos são definidos como parte dos eventos. No momento em que os eventos chegam à Adobe Analytics, esses eventos são traduzidos em dados mais estruturados que o Adobe Analytics pode manipular: exibições de página ou eventos de link.

O XDM não prescreve por si só como definir exibições de página ou eventos de link, nem instrui o Adobe Analytics sobre como tratar sua carga. Por exemplo, determinados campos XDM prontos para uso que parecem estar relacionados a exibições de página ou eventos de link, como `eventType`, `web.webPageDetails.pageViews`ou `web.webInteraction.linkEvents` são completamente independentes de implementação e não têm relevância para o Adobe Analytics.

Para lidar adequadamente com exibições de página e eventos de link, a seguinte lógica é aplicada ao envio de dados para a rede Adobe Experience Edge e encaminhada para a Adobe Analytics.

| A carga XDM contém... | Adobe Analytics. |
|---|---|
| `web.webPageDetails.name` ou `web.webPageDetails.URL` e não `web.webInteraction.type` | considera a carga um **exibição de página** |
| `web.webInteraction.type` e (`web.webInteraction.name` ou `web.webInteraction.url`) | considera a carga um **evento de link** |
| `web.webInteraction.type` e (`web.webPageDetails.name` ou `web.webPageDetails.url`) | considera a carga um **evento de link** <br/>`web.webPageDetails.name` e `web.webPageDetails.URL` estão definidos como `null` |
| não `web.webInteraction.type` e (não `webPageDetails.name` e não `web.webPageDetails.URL`) | elimina a carga e ignora os dados |

{style="table-layout:auto"}

Consulte a [Grupo de campos de esquema de Extensão completa do Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) para obter mais informações.
