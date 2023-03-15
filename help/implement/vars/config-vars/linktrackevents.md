---
title: linkTrackEvents
description: Determine quais eventos devem ser incluídos nas solicitações de imagem de rastreamento de link.
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 67%

---

# linkTrackEvents

Algumas implementações não querem incluir todas as variáveis em todas as solicitações de imagem de rastreamento de link. Use as variáveis [`linkTrackVars`](linktrackvars.md) e `linkTrackEvents` para incluir seletivamente dimensões e métricas em chamadas [`tl()`](../functions/tl-method.md).

Essa variável não é usada para chamadas de exibição de página (método [`t()`](../functions/t-method.md)).

## Determine quais eventos do Analytics incluir em um evento XDM usando o SDK da Web

O SDK da Web não exclui determinados campos para chamadas de rastreamento de link. No entanto, você pode usar a variável `onBeforeEventSend` retorno de chamada para limpar ou definir os campos desejados antes que os dados sejam enviados para o Adobe. Consulte [Modificação global de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) na documentação do SDK da Web para obter mais informações.

## Eventos em chamadas de rastreamento de link que usam a extensão do Adobe Analytics

A Adobe Experience Platform incluirá automaticamente eventos definidos em ocorrências de rastreamento de link se você não usar o código personalizado.

>[!IMPORTANT]
>
>Se você definir eventos no editor de código personalizado da extensão do Analytics, será necessário incluir o evento em `linkTrackEvents` usando o código personalizado também.

## s.linkTrackEvents no AppMeasurement e no editor de código personalizado da extensão do Analytics

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
