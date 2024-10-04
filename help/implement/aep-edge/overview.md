---
title: Implementar o Adobe Analytics com a Adobe Experience Platform Edge
description: Visão geral do uso de dados XDM da Experience Platform no Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: c7fd66e99fd7d6c474682621a3c18bf41d541a96
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 77%

---

# Implementar o Adobe Analytics com a rede de borda da Adobe Experience Platform

A rede de borda da Adobe Experience Platform permite enviar dados destinados a vários produtos a um local centralizado. A rede de borda encaminha as informações apropriadas para os produtos desejados. Esse conceito permite consolidar os esforços de implementação, especialmente abrangendo várias soluções de dados.

A Adobe oferece três formas principais de se enviar dados à rede de borda:

* **[SDK da Web da Adobe Experience Platform](web-sdk/overview.md)**: usar a extensão de SDK da Web da coleção de dados da Adobe Experience Platform para enviar dados para o Edge.
* **[SDK móvel da Adobe Experience Platform](mobile-sdk/overview.md)**: usar a extensão de SDK móvel da coleção de dados da Adobe Experience Platform para enviar dados para o Edge.
* **[API do servidor de rede de borda da Adobe Experience Platform](server-api/overview.md)**: envie dados diretamente à rede de borda usando uma API.



## Como o Adobe Analytics lida com os dados da rede de borda

Os dados enviados à rede de borda da Adobe Experience Platform podem ter dois formatos:

* Objeto de XDM: está em conformidade com esquemas baseados em [XDM (Experience Data Model, modelo de dados de experiência)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR). O XDM oferece flexibilidade sobre quais campos são definidos como parte dos eventos. Ao chegar no Adobe Analytics, os eventos são convertidos para um formato processável.
* Objeto de dados: envia dados à rede de borda por meio de campos específicos mapeados para o Adobe Analytics. A rede de borda detecta a presença desses campos e os encaminha para o Adobe Analytics, sem a necessidade de manter conformidade com um esquema.

O Edge Network usa a seguinte lógica para determinar exibições de página do Adobe Analytics e eventos de link:

| O conteúdo XDM contém... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL` (não `xdm.web.webInteraction.type`) | considera o conteúdo uma **exibição de página** |
| `xdm.eventType = web.webPageDetails.pageViews` | considera o conteúdo uma **exibição de página** |
| `xdm.web.webInteraction.type` e (`xdm.web.webInteraction.name` ou `xdm.web.webInteraction.url`) | considera o conteúdo um **evento de link** |
| `xdm.web.webInteraction.type` e (`xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.url`) | considera a carga um **evento de link** <br/>Também define `xdm.web.webPageDetails.name` e `xdm.web.webPageDetails.URL` como `null` |
| não `xdm.web.webInteraction.type` e (não `xdm.webPageDetails.name` e não `xdm.web.webPageDetails.URL`) | elimina o conteúdo e ignora os dados |

{style="table-layout:auto"}

Além de diferenciar exibições de página e cliques em links, a seguinte lógica está em vigor e determina se determinados eventos são categorizados como A4T ou são descartados.

| O conteúdo XDM contém... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` e `xdm._experience.decisioning` | considera a carga uma chamada **A4T**. |
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` e nenhum `xdm._experience.decisioning` | elimina o conteúdo e ignora os dados |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` e `xdm._experience.decisioning` e nenhum `web.webInteraction.type` | considera a carga uma chamada **A4T**. |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` e nenhum `xdm._experience.decisioning` e nenhum `web.webInteraction.type` | O elimina a carga e ignora os dados. |

{style="table-layout:auto"}

Consulte o [Grupo de campos de esquema de extensão completa de ExperienceEvent do Adobe Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) para mais informações.
