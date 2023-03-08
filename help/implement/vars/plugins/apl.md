---
title: apl (appendToList)
description: Anexe valores a variáveis que suportam vários valores.
feature: Variables
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 100%

---

# Plug-in da Adobe: apl (appendToList)

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `apl` permite adicionar com segurança novos valores a variáveis delimitadas por lista, como [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md) e outras.[`list`](../page-vars/list.md)

* Se o valor que você deseja adicionar não existir na variável, então o código adiciona o valor ao final da string.
* Se o valor que você deseja adicionar já existir na variável, esse plug-in não altera o valor. Esses recursos permitem que sua implementação evite valores duplicados.
* Se a variável que você deseja adicionar estiver vazia, o plug-in atribuirá à variável o novo valor.

A Adobe recomenda usar esse plug-in se você desejar adicionar novos valores às variáveis existentes que contenham uma string de valores delimitados. Esse plug-in não é necessário se você preferir concatenar strings para variáveis que contêm valores delimitados.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize APL (Append To List)
1. Save and publish the changes to the rule.-->

## Instale o plug-in usando o editor de código personalizado do

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `apl` usa os seguintes argumentos:

* **`lv`** (obrigatório, string): a variável que contém uma lista delimitada de itens aos quais será adicionado um novo valor
* **`vta`** (obrigatório, string): uma lista delimitada por vírgulas com novos valores a serem adicionados ao valor do argumento `lv`.
* **`d1`** (opcional, string): o delimitador usado para separar os valores individuais já contidos no argumento `lv`.  O padrão é uma vírgula (`,`) quando um valor não está definido.
* **`d2`** (opcional, string): o delimitador de saída. O padrão é o mesmo valor de `d1` quando não está definido.
* **`cc`** (opcional, booleano): um sinalizador que indica se uma verificação que diferencia maiúsculas e minúsculas é usada. Se `true`, a verificação de duplicação faz distinção entre maiúsculas e minúsculas. Se definida `false` ou não definida, a verificação de duplicação não diferencia maiúsculas de minúsculas. O padrão é `false`.

A função `apl` retorna o valor do argumento `lv` somado a quaisquer valores não duplicados no argumento `vta`.

## Exemplos

```js
// Set the events variable to "event22,event24,event23".
s.events = "event22,event24";
s.events = apl(s.events,"event23");

// The events variable remains unchanged because the apl function does not add duplicate values
s.events = "event22,event23";
s.events = apl(s.events,"event23");

// Set the events variable to "event23" if the events variable is blank
s.events = "";
s.events = apl(s.events,"event23");

// Append a value to eVar5. The value of prop4 remains unchanged.
// The value of eVar5 is "hello|people|today".
s.prop4 = "hello|people";
s.eVar5 = apl(s.prop4, "today", "|");

// Sets prop4 to "hello|people,today". Be mindful of correct delimiters!
s.prop4 = "hello|people";
s.prop4 = apl(s.prop4, "today");

// Sets the events variable to "event22,event23,EVentT23". Be mindful of capitalization when using the cc argument!
s.events = "event22,event23";
s.events = apl(s.events,"EVenT23", ",", ",", true);

// Sets the events variable to "event22,event23,event24,event25".
s.events = "event22,event23";
s.events = apl(s.events, "event23,event24,event25");

// Sets linkTrackVars to "events,eVar1,campaign".
// The last three arguments at the end of this apl call are not necessary because they match the default argument values.
s.linkTrackVars = "events,eVar1";
s.linkTrackVars = apl(s.linkTrackVars, "campaign", ",", ",", false);

// This apl call does not do anything because the code does not assign the returned value to a variable.
s.events = "event22,event24";
apl(s.events, "event23");

// Sets the list2 variable to "apple-APPLE-Apple".
// Since the two delimiter arguments are different, the value passed in is delimited by "|", then joined together by "-".
s.list2 = "apple|APPLE";
s.list2 = apl(s.list2, "Apple", "|", "-", true);

// Sets the list3 variable to "value1,value1,value1" (unchanged).
// Only new values are deduplicated. Existing duplicate values remain.
s.list3 = "value1,value1,value1";
s.list3 = apl(s.list3,"value1");
```

## Histórico da versão

### 4.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 3.2 (25 de setembro, 2019)

* Correção de problemas de compatibilidade com chamadas de `apl` que usavam versões anteriores do plug-in
* Remoção de avisos do console para redução do tamanho
* Adição de `inList 2.1`

### 3.1 (22 de abril, 2018)

* Agora, o padrão do argumento `d2`, quando não definido, é o valor do argumento `d1`

### 3.0 (16 de abril, 2018)

* Reanálise/reescrita completa do plug-in
* Foi adicionada a verificação avançada de erros
* O argumento `vta` agora aceita vários valores de uma vez
* Adição do argumento `d2` para formatar o valor de retorno
* Alteração do tipo do argumento `cc` para booleano

### 2.5 (18 de fevereiro de 2016)

* A função `inList` agora é usada para processamento de comparação

### 2.0 (26 de janeiro de 2016)

* O argumento `d` (delimitador) agora é opcional (o padrão é uma vírgula)
* O argumento `u` (sinalizador de diferenciação entre maiúsculas e minúsculas) agora é opcional (o padrão é não diferenciar maiúsculas de minúsculas)
* Independentemente do argumento `u` (sinalizador de diferenciação entre maiúsculas e minúsculas), o plug-in não anexa mais um valor a uma lista se o valor já existir na lista
