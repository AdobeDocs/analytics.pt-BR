---
title: linkTrackEvents
description: Determine quais eventos devem ser incluídos nas solicitações de imagem de rastreamento de link.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkTrackEvents

Algumas implementações não querem incluir todas as variáveis em todas as solicitações de imagem de rastreamento de link. Use as variáveis `linkTrackVars` e `linkTrackEvents` para incluir seletivamente dimensões e métricas em `tl()` chamadas.

Essa variável não é usada para chamadas de exibição de página (`t()` função).

## Eventos em chamadas de rastreamento de link usando o Adobe Experience Platform Launch

O Launch detecta automaticamente os eventos definidos na interface e os inclui nas ocorrências de rastreamento de link.

> [!IMPORTANT] Se você definir eventos no Launch usando o editor de código personalizado, deverá incluir o evento no `linkTrackEvents` uso do código personalizado também.

## s.linkTrackEvents no AppMeasurement e Iniciar editor de código personalizado

A `s.linkTrackEvents` variável é uma string contendo uma lista de eventos delimitada por vírgulas que você deseja incluir nas solicitações de imagem de rastreamento de link (`tl()` função). Os três critérios a seguir devem ser atendidos para incluir métricas nas ocorrências de rastreamento de link:

* Defina o evento desejado na `events` variável. Por exemplo, `s.events = "event1";`.
* Set the `events` variable in `linkTrackVars`. Por exemplo, `s.linkTrackVars = "events";`.
* Defina o evento desejado na `linkTrackEvents` variável. Por exemplo, `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

O valor padrão para essa variável é uma string vazia. Se essa variável não estiver definida, todos os eventos serão incluídos nas solicitações de imagem de rastreamento de link. Observe que o Launch preenche automaticamente essa variável com base nos eventos definidos na interface, de modo que seja sempre definido nas implementações usando o Launch.

> [!TIP] Evite usar o identificador de objeto do Analytics (`s.`) ao especificar eventos nessa variável. Por exemplo, `s.linkTrackEvents = "event1";` está correto, enquanto `s.linkTrackEvents = "s.event1";` está incorreto.

## Exemplo

A seguinte função de rastreamento de link inclui somente `event1` (não `event2`) na solicitação de imagem enviada à Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
