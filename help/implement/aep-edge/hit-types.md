---
title: Tipos de evento do Edge Network no Adobe Analytics
description: Como o Adobe Analytics interpreta os eventos recebidos da Edge Network.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 6e500007e10086c0ff8108856a3563d7702f1130
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 25%

---

# Tipos de evento do Edge Network no Adobe Analytics

O Adobe Analytics trata as ocorrências de forma diferente, dependendo das funções chamadas no AppMeasurement. Por exemplo, [`s.t`](/help/implement/vars/functions/t-method.md) e [`s.tl`](/help/implement/vars/functions/tl-method.md) incluem ou omitem determinadas dimensões e incrementam exibições de página de forma diferente. O Adobe Experience Platform contém apenas o comando `sendEvent`. As propriedades específicas na carga `xdm` determinam como esses dados são interpretados no Adobe Analytics.

O Edge Network usa a seguinte lógica para determinar exibições de página do Adobe Analytics e eventos de link:

| O conteúdo XDM contém... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL` (não `xdm.web.webInteraction.type`) | considera o conteúdo uma **exibição de página** |
| `xdm.eventType = web.webPageDetails.pageViews` | considera o conteúdo uma **exibição de página** |
| `xdm.web.webInteraction.type` e (`xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.url`) | considera a carga um **evento de link** <br/>Também define `xdm.web.webPageDetails.name` e `xdm.web.webPageDetails.URL` como `null` |
| nenhum `xdm.web.webInteraction.type` e nenhum `xdm.webPageDetails.name` e nenhum `xdm.web.webPageDetails.URL` | elimina o conteúdo e ignora os dados |

| A carga do objeto de dados contém... | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` ou `data.__adobe.analytics.pageURL` (não `data.__adobe.analytics.linkType`) | considera o conteúdo uma **exibição de página** |
| `data.__adobe.analytics.linkType` e (`data.__adobe.analytics.linkName` ou `data.__adobe.analytics.linkURL`) | considera a carga um **evento de link** <br/>Também define `data.__adobe.analytics.pageName` e `data.__adobe.analytics.pageURL` como `null` |
| nenhum `data.__adobe.analytics.linkType` e nenhum `data.__adobe.analytics.pageName` e nenhum `data.__adobe.analytics.pageURL` | elimina o conteúdo e ignora os dados |

>[!NOTE]
>
>Se você incluir um objeto `xdm` e um objeto `data` na mesma carga, o Adobe Analytics verificará os dois objetos em busca dos respectivos campos.

Além de diferenciar exibições de página e cliques em links, a seguinte lógica está em vigor e determina se determinados eventos são categorizados como A4T ou são descartados.

| O conteúdo XDM contém... | Adobe Analytics... |
|---|---|
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` e `xdm._experience.decisioning` | considera a carga uma chamada **A4T**. |
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` e nenhum `xdm._experience.decisioning` | elimina o conteúdo e ignora os dados |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` e `xdm._experience.decisioning` e nenhum `web.webInteraction.type` | considera a carga uma chamada **A4T**. |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` e nenhum `xdm._experience.decisioning` e nenhum `web.webInteraction.type` | O elimina a carga e ignora os dados. |

Consulte o [Grupo de campos de esquema de extensão completa de ExperienceEvent do Adobe Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) para mais informações.
