---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkTrackVars

A variável é uma lista separada por vírgulas de variáveis enviadas com links personalizados, de saída e de download.

The [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) parameter should include each variable that you want to track with every file download, exit link, and custom link.

The settings for `linkTrackVars` and `linkTrackEvents` within the JS file affect every file download, exit link, and custom link. É possível aumentar instâncias de cada variável e evento em situações em que a variável (ou evento) se aplica à página atual, mas não ao download de arquivo específico, link de saída, ou link personalizado.

Para garantir que as variáveis adequadas sejam definidas com o código de link personalizado, a Adobe recomenda configurar `linkTrackVars` e `linkTrackEvents` dentro do código de link personalizado, da seguinte forma:

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

The values of `linkTrackVars` and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

*Observação: Se`linkTrackVars`(ou`linkTrackEvents`) for nulo (ou uma sequência vazia, como ""), todas as variáveis (ou eventos) do Analytics definidas para a página atual serão rastreadas. Em outras palavras, todas as variáveis com valores seriam enviadas com dados de link. Provavelmente, isso aumentará as instâncias de cada variável. Para evitar a inflação de instâncias ou exibições de página associadas a outras variáveis, a Adobe recomenda preencher`linkTrackVars`e`linkTrackEvents`no evento[!UICONTROL onClick]de um link usado para o rastreamento de link.*

Todas as variáveis que devem ser enviadas com os dados do link (personalizado, de saída e download) devem ser listadas em `linkTrackVars`. Se `linkTrackEvents` for usado, `linkTrackVars` deverá conter "events".

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | Qualquer | "Nenhum" |

When populating `linkTrackVars`, do not use the 's.' prefix for variables. Por exemplo, em vez de preencher `linkTrackVars` com "s.prop1", você deve preencher com "prop1". O exemplo a seguir ilustra como `linkTrackVars` deve ser usado.

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

Como o link para o google.com é um link de saída (a menos que você seja a Google), event1 e eVar1 são enviados com os dados de link de saída, aumentando as instâncias associadas com eVar1 e o número de vezes que event1 é acionada. No link para [!DNL test.php], [!UICONTROL eVar1] é enviada com um valor de 'value C', pois esse é o valor atual de eVar1 quando `tl()` é chamado.

## Sintaxe e valores possíveis

A variável `linkTrackVars` é uma lista de nomes de variáveis separados por vírgulas que faz distinção entre maiúsculas e minúsculas, sem o prefixo do nome do objeto. Use 'eVar1' em vez de 's.eVar1'.

```
s.linkTrackVars="variable_name[,variable_name[...]]"
```

A variável `linkTrackVars` variable may contain only variables that are sent to [!DNL Analytics], namely: `events`, `campaign`, `purchaseID`, `products`, `eVar1-75`, `prop1-75`, `hier1-5`, `channel`, `server`, `state`, `zip`, and `pageType`.

## Exemplos

```
s.linkTrackVars="events,prop1,eVar49"
```

```
s.linkTrackVars="products"
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

* Se `linkTrackVars` estiver em branco, todas as variáveis que têm valores serão rastreadas com todas as chamadas do servidor.
* Qualquer variável listada em `linkTrackVars`, que tem um valor no momento de qualquer link de download, de saída ou personalizado, é rastreada.
* Se `linkTrackEvents` for usado, `linkTrackVars` deverá conter "events".

* Não use o prefixo "s." ou "s_objectname". para variáveis.
