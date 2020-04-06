---
title: linkTrackEvents
description: Determine quais eventos devem ser incluídos nas solicitações de imagem de rastreamento de link.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkTrackEvents

Algumas implementações não querem incluir todas as variáveis em todas as solicitações de imagem de rastreamento de link. Use as variáveis [`linkTrackVars`](linktrackvars.md) e `linkTrackEvents` para incluir seletivamente dimensões e métricas em chamadas [`tl()`](../functions/tl-method.md).

This variable is not used for page view calls ([`t()`](../functions/t-method.md) method).

## Eventos em chamadas de rastreamento de link que usam o Adobe Experience Platform Launch

O Launch detecta automaticamente os eventos definidos na interface e os inclui nas ocorrências de rastreamento de link.

>[!IMPORTANT] Se você definir eventos no Launch usando o editor de código personalizado, também deverá incluir o evento no `linkTrackEvents` uso do código personalizado.

## s.linkTrackEvents no AppMeasurement e no editor de código personalizado do Launch

The `s.linkTrackEvents` variable is a string containing a comma-delimited list of events that you want to include in link tracking image requests (`tl()` method). Os três critérios a seguir devem ser atendidos para incluir métricas nas ocorrências de rastreamento de link:

* Defina o evento desejado na variável [`events`](../page-vars/events/events-overview.md). Por exemplo, `s.events = "event1";`.
* Defina a variável `events` no `linkTrackVars`. Por exemplo, `s.linkTrackVars = "events";`.
* Defina o evento desejado na variável `linkTrackEvents`. Por exemplo, `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

O valor padrão para essa variável é uma cadeia de caracteres vazia. Se essa variável não estiver definida, todos os eventos serão incluídos nas solicitações de imagem de rastreamento de link. Observe que o Launch preenche automaticamente essa variável com base nos eventos definidos na interface, de modo que seja sempre definido nas implementações usando o Launch.

>[!TIP] Evite usar o identificador de objeto do Analytics (`s.`) ao especificar eventos nessa variável. Por exemplo, `s.linkTrackEvents = "event1";` está correto, enquanto `s.linkTrackEvents = "s.event1";` está incorreto.

## Exemplo

A seguinte função de rastreamento de link inclui somente `event1` (não `event2`) na solicitação de imagem enviada à Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
