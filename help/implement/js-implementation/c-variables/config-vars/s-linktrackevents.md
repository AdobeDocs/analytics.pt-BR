---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: ca0797a353661a72d4064aa5aa84c3d9b7eb38a5

---


# s.linkTrackEvents

A variável é uma lista de eventos separada por vírgulas enviada com um link personalizado, de saída ou de download. O parâmetro `linkTrackEvents` deve incluir todos os eventos que você quer rastrear com cada download de arquivo, link de saída e link personalizado. Quando um desses tipos de link ocorrer, o valor atual de cada variável identificado será acompanhado. Essa variável só é considerada se [`linkTrackVars`](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) contiver "events".

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | N/D | Conversão | "Nenhum" |

Se um evento não estiver em `linkTrackEvents`, ele não será enviado para o Analytics, mesmo se for preenchido no evento `onClick` de um link, como mostrado no exemplo a seguir:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

Os valores [`linkTrackVars`](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) e `linkTrackEvents`substituem as configurações no arquivo JS e garantem que apenas as variáveis e os eventos especificados no código do link personalizado sejam definidos para o link específico. As configurações de ambos afetam cada download de arquivo, link de saída e link personalizado. É possível aumentar instâncias de cada variável e evento em situações em que a variável (ou evento) se aplica à página atual, mas não ao download de arquivo específico, link de saída, ou link personalizado.

Para garantir que as variáveis adequadas estejam definidas com o código de link personalizado, a Adobe recomenda definir  *`linkTrackVars`* e *`linkTrackEvents`* no código de link personalizado, como mostrado a seguir:

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

No exemplo acima, o valor de `prop1` está definido dentro do próprio código do link personalizado. O valor de `prop2` vem do valor atual da variável, como definido na página.

*Observação: se`linkTrackVars`(ou`linkTrackEvents`) for nulo (ou uma cadeia de caracteres vazia), todas as variáveis do Analytics (ou eventos) definidas para a página atual serão rastreadas. Em outras palavras, todas as variáveis com valores seriam enviadas com dados de link. Isso provavelmente aumentará as instâncias de cada variável. Para evitar a inflação de instâncias ou exibições de página associadas a outras variáveis, a Adobe recomenda preencher`linkTrackVars`e`linkTrackEvents`no evento`onClick`de um link usado para o rastreamento de link.*

Todas as variáveis que devem ser enviadas com os dados do link (personalizado, de saída e download) devem ser listadas em `linkTrackVars`. Se `linkTrackEvents` for usado, `linkTrackVars` deverá conter "events".

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | N/D | Qualquer | "Nenhum" |

Ao preencher o `linkTrackEvents`, não use o prefixo 's.' para variáveis. Por exemplo, em vez de preencher com "s.event1", você deve preencher com "event1". O exemplo a seguir ilustra como deve ser usado.

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

No primeiro link, observe que a variável de eventos retém o valor definido antes do clique no link. Isso permite que `event1` seja enviado com o link personalizado. No segundo exemplo, o link para `event2` não é registrado porque não está listado em `linkTrackEvents`.

Para evitar confusão e possíveis problemas, a Adobe recomenda preencher [`linkTrackVars`](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) e `linkTrackEvents` no evento `onClick` de um link usado para o rastreamento de links.

## Sintaxe e valores possíveis

A variável *`linkTrackEvents`* é uma lista de eventos separada por vírgulas (sem espaços).

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Somente os nomes de eventos são permitidos em `linkTrackEvents`. Esses eventos estão listados em [Eventos](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/analytics-basics/ref-events.html). Se um espaço for exibido antes ou depois do nome do evento, o evento não poderá ser enviado com nenhuma solicitação de imagem de link.

## Exemplos

Para monitorar `prop1`, `eVar1` e `event1` com todos os downloads de arquivo, links de saída e links personalizados, use as seguintes configurações no arquivo JS global:

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

* Tenha em mente que se um evento for acionado em uma página e listado em `linkTrackEvents`. Esse evento será gravado novamente com qualquer link de saída, de download ou personalizado, a menos que a variável de eventos seja redefinida antes desse evento (no `onClick` de um link ou depois da chamada para a função `t()`).

* Se `linkTrackEvents` contiver espaços entre os nomes de evento, os eventos não serão gravados.
