---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkTrackEvents

A variável é uma lista de eventos separada por vírgulas enviada com um [!UICONTROL link personalizado], [!UICONTROL de saída] ou [!UICONTROL de download].

Se um evento não estiver em *`linkTrackEvents`*, ele não será enviado para o [!DNL Analytics], mesmo se for preenchido no evento [!UICONTROL onClick] de um link, como mostrado no exemplo a seguir:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

No primeiro link para [!DNL help.php], observe que a variável de eventos retém o valor definido antes do clique no link. Isso permite que event1 seja enviado com o link personalizado. No segundo exemplo, o link para [!DNL test.php], event2 não é registrado porque não está listado em *`linkTrackEvents`*.

Para evitar confusão e possíveis problemas, a Adobe recomenda preencher *`linkTrackVars`* e *`linkTrackEvents`* no evento [!UICONTROL onClick] de um link usado para o rastreamento de links.

A variável *`linkTrackEvents`* contém os eventos que devem ser enviados com links [!UICONTROL personalizados], [!UICONTROL de download] e [!UICONTROL de saída]. Essa variável só é considerada se *`linkTrackVars`* contiver "events".

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Conversão | "Nenhum" |

## Sintaxe e valores possíveis

A variável *`linkTrackEvents`* é uma lista de eventos separada por vírgulas (sem espaços).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Somente os nomes de eventos são permitidos em *`linkTrackEvents`*. Esses eventos estão listados em [Eventos](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Se um espaço for exibido antes ou depois do nome do evento, o evento não poderá ser enviado com nenhuma solicitação de imagem de link.

## Exemplos

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

* O arquivo JavaScript só usa *`linkTrackEvents`*, se *`linkTrackVars`* contiver a variável "events". "events" deve ser incluído *`linkTrackVars`* somente quando *`linkTrackEvents`* estiver definido.

* Tenha em mente que se um evento for acionado em uma página e listado em *`linkTrackEvents`*. Esse evento será gravado novamente com qualquer link [!UICONTROL de saída], [!UICONTROL de download] ou [!UICONTROL personalizado], a menos que a variável de eventos seja redefinida antes desse evento (no [!UICONTROL onClick] de um link ou depois da chamada para a função *`t()`*).

* Se *`linkTrackEvents`* contiver espaços entre os nomes de evento, os eventos não serão gravados.
