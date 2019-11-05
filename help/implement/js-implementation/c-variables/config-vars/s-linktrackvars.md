---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.linkTrackVars

A variável é uma lista separada por vírgulas de variáveis enviadas com links personalizados, de saída e de download.

Se *`linkTrackVars`* for definido como "", todas as variáveis com valores serão enviadas com dados de link. Para evitar a inflação de instâncias ou exibições de página associadas a outras variáveis, a Adobe recomenda preencher *`linkTrackVars`* e *`linkTrackEvents`* no evento [!UICONTROL onClick] de um link usado para o rastreamento de link.

Todas as variáveis que devem ser enviadas com os dados do link (personalizado, de saída e download) devem ser listadas em *`linkTrackVars`*. Se *`linkTrackEvents`* for usado, *`linkTrackVars`* deverá conter "events".

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Qualquer | "Nenhum" |

When populating *`linkTrackVars`*, do not use the 's.' prefix for variables. Por exemplo, em vez de preencher *`linkTrackVars`* com "s.prop1", você deve preencher com "prop1". O exemplo a seguir ilustra como *`linkTrackVars`* deve ser usado.

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

Como o link para o google.com é um link de saída (a menos que você seja a Google), event1 e eVar1 são enviados com os dados de link de saída, aumentando as instâncias associadas com eVar1 e o número de vezes que event1 é acionada. No link para [!DNL test.php], [!UICONTROL eVar1] é enviada com um valor de 'value C', pois esse é o valor atual de [!UICONTROL eVar1] quando *`tl()`* é chamado.

## Sintaxe e valores possíveis

A variável *`linkTrackVars`* é uma lista de nomes de variáveis separados por vírgulas que faz distinção entre maiúsculas e minúsculas, sem o prefixo do nome do objeto. Use 'eVar1' em vez de 's.eVar1'.

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

A variável A variável *`linkTrackVars`* pode conter somente variáveis enviadas para [!DNL Analytics], a saber: *`events`*, *`campaign`*, *`purchaseID`*, *`products`*, [!UICONTROL eVar1-75], [!UICONTROL prop1-75], [!UICONTROL hier1-5], *`channel`*, *`server`*, *`state`*, *`zip`* e *`pageType`*.

## Exemplos

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

* Se *`linkTrackVars`* estiver em branco, todas as variáveis que têm valores serão rastreadas com todas as chamadas do servidor.
* Qualquer variável listada em *`linkTrackVars`*, que tem um valor no momento de qualquer link de download, de saída ou personalizado, é rastreada.
* Se *`linkTrackEvents`* for usado, *`linkTrackVars`* deverá conter "events".

* Não use o prefixo "s." ou "s_objectname". para variáveis.
