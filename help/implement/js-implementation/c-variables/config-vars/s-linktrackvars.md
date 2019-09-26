---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkTrackVars

A variável é uma lista separada por vírgulas de variáveis enviadas com links personalizados, de saída e de download.

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. Para evitar inflação de instâncias ou exibições de página associadas a outras variáveis, a Adobe recomenda preencher *`linkTrackVars`* e *`linkTrackEvents`* no evento [!UICONTROL onClick] de um link usado para o rastreamento de link.

Todas as variáveis que devem ser enviadas com os dados do link (personalizado, de saída e download) devem ser listadas em *`linkTrackVars`*. Se *`linkTrackEvents`* for usado, *`linkTrackVars`* deverá conter "events".

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Qualquer | "Nenhuma" |

No preenchimento de *`linkTrackVars`*, não use o prefixo 's.' para variáveis. Por exemplo, em vez de preencher *`linkTrackVars`* com "s.prop1", você deve preenchê-lo com "prop1". O exemplo a seguir ilustra como *`linkTrackVars`* deve ser usado.

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

Como o link para o google.com é um link de saída (a menos que você seja a Google), event1 e eVar1 são enviados com os dados de link de saída, aumentando as instâncias associadas com eVar1 e o número de vezes que event1 é acionada. In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

## Sintaxe e valores possíveis

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. Use 'eVar1' em vez de 's.eVar1'.

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

A variável *`linkTrackVars`* pode conter somente variáveis enviadas para [!DNL Analytics], a saber: *`events`*, *`campaign`*, *`purchaseID`*, *`products`*, [!UICONTROL eVar1-75], [!UICONTROL prop1-75], [!UICONTROL hier1-5]*`channel`**`server`**`state`**`zip`**`pageType`*, , , , e .

## Exemplos

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## Configurações

Nenhuma

## Armadilhas, dúvidas e dicas

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* Se *`linkTrackEvents`* for usado, *`linkTrackVars`* deverá conter "events".

* Não use o prefixo "s." ou "s_objectname". para variáveis.