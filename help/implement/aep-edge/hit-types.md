---
title: Tipos de evento do Edge Network no Adobe Analytics
description: Como o Adobe Analytics interpreta os eventos recebidos da Edge Network.
feature: Implementation Basics
role: Admin, Developer
exl-id: 31085025-9c38-4375-8dfb-4fded6542ca7
source-git-commit: 0096a53505b3b1bc925c813c2c6c11ee3c7ee0c0
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 20%

---

# Tipos de evento do Edge Network no Adobe Analytics

O Adobe Analytics trata as ocorrências de forma diferente, dependendo das funções chamadas no AppMeasurement. Por exemplo, [`s.t`](/help/implement/vars/functions/t-method.md) e [`s.tl`](/help/implement/vars/functions/tl-method.md) incluem ou omitem determinadas dimensões e incrementam [exibições de página](/help/components/metrics/page-views.md) de forma diferente. O Adobe Experience Platform contém apenas o comando [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/overview). As propriedades específicas na carga [`xdm`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/js/commands/sendevent/xdm) ou [`data`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/data) determinam como esses dados são interpretados no Adobe Analytics.

O Edge Network usa a seguinte lógica para determinar as [exibições de página](/help/components/metrics/page-views.md) e os [eventos de link](/help/components/metrics/page-events.md) do Adobe Analytics:

## Exibições de página e eventos de link usando o objeto `xdm`

| O conteúdo XDM contém... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL` (não `xdm.web.webInteraction.type`) | considera o conteúdo uma **exibição de página** |
| `xdm.eventType = web.webpagedetails.pageViews` | considera o conteúdo uma **exibição de página** |
| `xdm.web.webInteraction.type` e (`xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL`) | considera a carga um **evento de link** <br/>Também define `xdm.web.webPageDetails.name` e `xdm.web.webPageDetails.URL` como `null` |
| `xdm.web.webInteraction.type` e (`xdm.web.webInteraction.name` ou `xdm.web.webInteraction.URL`) | considera a carga um **evento de link** <br/>Também define `xdm.web.webPageDetails.name` e `xdm.web.webPageDetails.URL` como `null`, se presente |
| nenhum `xdm.web.webInteraction.type` e nenhum `xdm.web.webPageDetails.name` e nenhum `xdm.web.webPageDetails.URL` | elimina o conteúdo e ignora os dados |

>[!TIP]
>
>Os nomes de campos XDM na carga diferenciam maiúsculas de minúsculas (por exemplo, `webPageDetails.URL`). O campo `xdm.eventType` é um valor de cadeia de caracteres com seu próprio conjunto de valores aceitos, e a capitalização desses valores pode não corresponder aos nomes dos campos XDM. Para obter os valores aceitos, consulte o campo `eventType` na [classe XDM ExperienceEvent](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/classes/experienceevent#eventType).

+++Exibição de página mínima usando `xdm` campos

```json
{
  "xdm": {
    "web": {
      "webPageDetails": {
        "name": "Example page",
        "URL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Exibição de página mínima usando `xdm.eventType`

```json
{
  "xdm": {
    "eventType": "web.webpagedetails.pageViews"
  }
}
```

+++

+++Evento de link mínimo usando campos recomendados

```json
{
  "xdm": {
    "web": {
      "webInteraction": {
        "type": "other",
        "name": "Header nav: Pricing",
        "URL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

## Exibições de página e eventos de link usando o objeto `data`

| A carga do objeto de dados contém... | Adobe Analytics... |
|---|---|
| `data.__adobe.analytics.pageName` ou `data.__adobe.analytics.pageURL` (não `data.__adobe.analytics.linkType`) | considera o conteúdo uma **exibição de página** |
| `data.__adobe.analytics.linkType` e (`data.__adobe.analytics.linkName` ou `data.__adobe.analytics.linkURL`) | considera a carga um **evento de link** <br/>Também define `data.__adobe.analytics.pageName` e `data.__adobe.analytics.pageURL` como `null` |
| nenhum `data.__adobe.analytics.linkType` e nenhum `data.__adobe.analytics.pageName` e nenhum `data.__adobe.analytics.pageURL` | elimina o conteúdo e ignora os dados |

+++Exibição de página mínima usando `data` campos

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "pageName": "Example page",
        "pageURL": "https://example.com/page"
      }
    }
  }
}
```

+++

+++Evento de link mínimo usando `data` campos

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "linkType": "o",
        "linkName": "Header nav: Pricing",
        "linkURL": "https://example.com/pricing"
      }
    }
  }
}
```

+++

>[!NOTE]
>
>Se você incluir um objeto `xdm` e um objeto `data` na mesma carga, o Adobe Analytics verificará os dois objetos em busca dos respectivos campos.

## Eventos relacionados ao A4T e à decisão

Além de diferenciar exibições de página e eventos de link, a lógica a seguir determina se determinados eventos de decisão são categorizados como A4T ou são descartados.

| O conteúdo XDM contém... | Adobe Analytics... |
|---|---|
| `xdm.eventType = decisioning.propositionDisplay` e `xdm._experience.decisioning` | considera a carga uma chamada **A4T**. |
| `xdm.eventType = decisioning.propositionDisplay` e nenhum `xdm._experience.decisioning` | elimina o conteúdo e ignora os dados |
| `xdm.eventType = decisioning.propositionInteract` e `xdm._experience.decisioning` e não `xdm.web.webInteraction.type` | considera a carga uma chamada **A4T**. |
| `xdm.eventType = decisioning.propositionInteract` e nenhum `xdm._experience.decisioning` e nenhum `xdm.web.webInteraction.type` | O elimina a carga e ignora os dados. |
| `xdm.eventType = decisioning.propositionFetch` | elimina o conteúdo e ignora os dados |

>[!TIP]
>
>Os seguintes valores `eventType` estão obsoletos. Observe que esses valores afetam a lógica da mesma forma que seus equivalentes atuais:
>
>* O tipo de evento `display` está obsoleto. Use `decisioning.propositionDisplay` no lugar dela.
>* O tipo de evento `click` está obsoleto. Use `decisioning.propositionInteract` no lugar dela.
>* O tipo de evento `personalization.request` está obsoleto. Use `decisioning.propositionFetch` no lugar dela.

+++Exibição mínima do A4T

```json
{
  "xdm": {
    "eventType": "decisioning.propositionDisplay",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "display": 1 }
      }
    }
  }
}
```

+++

+++Interação mínima do A4T

```json
{
  "xdm": {
    "eventType": "decisioning.propositionInteract",
    "_experience": {
      "decisioning": {
        "propositions": [
          {
            "id": "example-proposition-id",
            "scope": "example-scope",
            "scopeDetails": { "decisionProvider": "AJO" }
          }
        ],
        "propositionEventType": { "interact": 1 }
      }
    }
  }
}
```

+++

Consulte o [Grupo de campos de esquema de extensão completa de ExperienceEvent do Adobe Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/field-groups/event/analytics-full-extension) para mais informações.
