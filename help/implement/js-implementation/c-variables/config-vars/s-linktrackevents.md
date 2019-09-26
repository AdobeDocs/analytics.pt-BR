---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkTrackEvents

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

No primeiro link para [!DNL help.php], observe que a variável de eventos retém o valor definido antes do clique no link, Isso permite que event1 seja enviado com o link personalizado. No segundo exemplo, o link para [!DNL test.php], event2 não é registrado porque não está listado em *`linkTrackEvents`*.

Para evitar confusão e possíveis problemas, a Adobe recomenda preencher *`linkTrackVars`* e *`linkTrackEvents`* no evento [!UICONTROL onClick] de um link usado para o rastreamento de links.

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. This variable is only considered if  contains "events."*`linkTrackVars`*

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Conversão | "Nenhuma" |

## Sintaxe e valores possíveis

A sintaxe de variável *`linkTrackEvents`* é uma lista de eventos separada por vírgulas (sem espaços).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Somente os nomes de eventos são permitidos em *`linkTrackEvents`*. These events are listed in [Events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Se um espaço for exibido antes ou depois do nome do evento, o evento não poderá ser enviado com nenhuma solicitação de imagem de link.

## Exemplos

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Configurações

Nenhuma

## Armadilhas, dúvidas e dicas

* O arquivo JavaScript só usará *`linkTrackEvents`* if *`linkTrackVars`* contains the "events" variable. "events" should be included in  only when  is defined.*`linkTrackVars`**`linkTrackEvents`*

* Tenha em mente que se um evento for acionado em uma página e listado em *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.
