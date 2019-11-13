---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 82060388a9a2122b66c57725cafa0eb4ce54e147

---


# s.linkTrackEvents

A variável é uma lista de eventos separada por vírgulas enviada com um link personalizado, de saída ou de download. The `linkTrackEvents` parameter should include each event you want to track with every file download, exit link, and custom link. Quando um desses tipos de link ocorrer, o valor atual de cada variável identificado será acompanhado. Essa variável só é considerada se `linkTrackVars` contiver "events".

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Conversão | "Nenhum" |

If an event is not in `linkTrackEvents`, it is not sent to Analytics, even if it is populated in the `onClick` event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

The values of [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link. As configurações de ambos afetam cada download de arquivo, link de saída e link personalizado. As instâncias de cada variável e evento podem ser infladas em situações em que a variável (ou evento) se aplica à página atual, mas não ao download de arquivo específico, link de saída ou link personalizado.

Para garantir que as variáveis adequadas sejam definidas com o código de link personalizado, a Adobe recomenda configurar *`linkTrackVars`* e *`linkTrackEvents`* dentro do código de link personalizado, da seguinte forma:

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

No exemplo acima, o valor para prop1 é definido no próprio código de link personalizado. O valor de prop2 vem do valor atual da variável, como definido na página.

*Observação: Se`linkTrackVars`(ou`linkTrackEvents`) for nulo (ou uma sequência vazia, como ""), todas as variáveis (ou eventos) do Analytics definidas para a página atual serão rastreadas. Em outras palavras, todas as variáveis com valores seriam enviadas com dados de link. Provavelmente, isso aumentará as instâncias de cada variável. Para evitar a inflação de instâncias ou exibições de página associadas a outras variáveis, a Adobe recomenda preencher`linkTrackVars`e`linkTrackEvents`no evento[!UICONTROL onClick]de um link usado para o rastreamento de link.*

Todas as variáveis que devem ser enviadas com os dados do link (personalizado, de saída e download) devem ser listadas em `linkTrackVars`. Se `linkTrackEvents` for usado, `linkTrackVars` deverá conter "events".

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Qualquer | "Nenhum" |

When populating `linkTrackEvents`, do not use the 's.' prefix for variables. Por exemplo, em vez de preenchê-lo com "s.event1", você deve preenchê-lo com "event1". O exemplo a seguir ilustra como deve ser usado.

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

No primeiro link, observe que a variável events retém o valor definido antes do clique no link. Isso permite que event1 seja enviado com o link personalizado. In the second example, the link to event2 is not recorded because it is not listed in `linkTrackEvents`.

Para evitar confusão e possíveis problemas, a Adobe recomenda preencher [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) e `linkTrackEvents` no evento `onClick` de um link usado para o rastreamento de links.

## Sintaxe e valores possíveis

A variável *`linkTrackEvents`* é uma lista de eventos separada por vírgulas (sem espaços).

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Somente os nomes de eventos são permitidos em `linkTrackEvents`. Esses eventos estão listados em [Eventos](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Se um espaço for exibido antes ou depois do nome do evento, o evento não poderá ser enviado com nenhuma solicitação de imagem de link.

## Exemplos

To track `prop1`, `eVar1`, and `event1` with every file download, exit link, and custom link, use the following settings within the global JS file:

```
s.linkTrackVars="prop1,eVar1,events"
```

```
s.linkTrackEvents="event1"
```

**Mais exemplos**

```
s.linkTrackEvents="purchase,event1"
```

```
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

* O arquivo JavaScript só usa `linkTrackEvents`, se `linkTrackVars` contiver a variável "events". "events" deve ser incluído `linkTrackVars` somente quando `linkTrackEvents` estiver definido.

* Tenha em mente que se um evento for acionado em uma página e listado em `linkTrackEvents`. Esse evento será gravado novamente com qualquer link [!UICONTROL de saída], [!UICONTROL de download] ou [!UICONTROL personalizado], a menos que a variável de eventos seja redefinida antes desse evento (no [!UICONTROL onClick] de um link ou depois da chamada para a função `t()`).

* Se `linkTrackEvents` contiver espaços entre os nomes de evento, os eventos não serão gravados.
