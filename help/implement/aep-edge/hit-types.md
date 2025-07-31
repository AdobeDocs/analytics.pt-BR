---
title: Tipos de evento do Edge Network no Adobe Analytics
description: Como o Adobe Analytics interpreta os eventos recebidos da Edge Network.
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 8d369bd3be3ae9c075e490e108666728a2cff5dc
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 28%

---

# Tipos de evento do Edge Network no Adobe Analytics

O Adobe Analytics trata as ocorrências de forma diferente, dependendo das funções chamadas no AppMeasurement. Por exemplo, [`s.t`](/help/implement/vars/functions/t-method.md) e [`s.tl`](/help/implement/vars/functions/tl-method.md) incluem ou omitem determinadas dimensões e incrementam exibições de página de forma diferente. O Adobe Experience Platform contém apenas o comando `sendEvent`. As propriedades específicas na carga `xdm` determinam como esses dados são interpretados no Adobe Analytics.

O Edge Network usa a seguinte lógica para determinar exibições de página do Adobe Analytics e eventos de link:

| O conteúdo XDM contém... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL` (não `xdm.web.webInteraction.type`) | considera o conteúdo uma **exibição de página** |
| `xdm.eventType = web.webPageDetails.pageViews` | considera o conteúdo uma **exibição de página** |
| `xdm.web.webInteraction.type` e (`xdm.web.webInteraction.name` ou `xdm.web.webInteraction.url`) | considera o conteúdo um **evento de link** |
| `xdm.web.webInteraction.type` e (`xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.url`) | considera a carga um **evento de link** <br/>Também define `xdm.web.webPageDetails.name` e `xdm.web.webPageDetails.URL` como `null` |
| não `xdm.web.webInteraction.type` e (não `xdm.webPageDetails.name` e não `xdm.web.webPageDetails.URL`) | elimina o conteúdo e ignora os dados |

Além de diferenciar exibições de página e cliques em links, a seguinte lógica está em vigor e determina se determinados eventos são categorizados como A4T ou são descartados.

| O conteúdo XDM contém... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` e `xdm._experience.decisioning` | considera a carga uma chamada **A4T**. |
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` e nenhum `xdm._experience.decisioning` | elimina o conteúdo e ignora os dados |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` e `xdm._experience.decisioning` e nenhum `web.webInteraction.type` | considera a carga uma chamada **A4T**. |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` e nenhum `xdm._experience.decisioning` e nenhum `web.webInteraction.type` | O elimina a carga e ignora os dados. |

Consulte o [Grupo de campos de esquema de extensão completa de ExperienceEvent do Adobe Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) para mais informações.
