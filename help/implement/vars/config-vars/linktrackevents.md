---
title: linkTrackEvents
description: Determine quais eventos devem ser incluídos nas solicitações de imagem de rastreamento de link.
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 100%

---

# linkTrackEvents

Algumas implementações não querem incluir todas as variáveis em todas as solicitações de imagem de rastreamento de link. Use as variáveis [`linkTrackVars`](linktrackvars.md) e `linkTrackEvents` para incluir seletivamente dimensões e métricas em chamadas [`tl()`](../functions/tl-method.md).

Essa variável não é usada para chamadas de exibição de página (método [`t()`](../functions/t-method.md)).

## Eventos em chamadas de rastreamento de link que usam tags na Adobe Experience Platform

A Adobe Experience Platform incluirá automaticamente eventos definidos em ocorrências de rastreamento de link se você não usar o código personalizado.

>[!IMPORTANT]
>
>Se você definir eventos na interface da Coleção de dados usando o editor de código personalizado, será necessário incluir o evento no `linkTrackEvents` que também usa código personalizado.

## s.linkTrackEvents no AppMeasurement e no editor de código personalizado do 

A variável `s.linkTrackEvents` é uma cadeia de caracteres quem contém uma lista de eventos delimitada por vírgulas que você deseja incluir nas solicitações de imagem de rastreamento de link (método `tl()`). Os três critérios a seguir devem ser atendidos para incluir métricas nas ocorrências de rastreamento de link:

* Defina o evento desejado na variável [`events`](../page-vars/events/events-overview.md). Por exemplo, `s.events = "event1";`.
* Defina a variável `events` no `linkTrackVars`. Por exemplo, `s.linkTrackVars = "events";`.
* Defina o evento desejado na variável `linkTrackEvents`. Por exemplo, `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

O valor padrão para essa variável é uma cadeia de caracteres vazia. Se essa variável não estiver definida, todos os eventos serão incluídos nas solicitações de imagem de rastreamento de link. Observe que a Coleção de dados preenche automaticamente essa variável com base nos eventos definidos na interface, de modo que seja sempre definida para implementações que usam tags na Adobe Experience Platform.

>[!TIP]
>
>Evite usar o identificador de objeto do Analytics (`s.`) ao especificar eventos nessa variável. Por exemplo, `s.linkTrackEvents = "event1";` está correto, enquanto `s.linkTrackEvents = "s.event1";` está incorreto.

## Exemplo

A seguinte função de rastreamento de link inclui somente `event1` (não `event2`) na solicitação de imagem enviada à Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
