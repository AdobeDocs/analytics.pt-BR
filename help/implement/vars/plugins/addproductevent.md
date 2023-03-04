---
title: addProductEvent
description: Adiciona eventos personalizados às variáveis products e events.
feature: Variables
exl-id: 74f4cb93-714a-4d2b-88f3-408d032f6811
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 100%

---

# Plug-in da Adobe: addProductEvent

{{plug-in}}

O plug-in `addProductEvent` adiciona um evento numérico ou de moeda à variável [`products`](../page-vars/products.md). A Adobe recomenda usar esse plug-in se você quiser adicionar um evento numérico ou de moeda à variável `products` sem se preocupar com o formato da string do produto. Esse plug-in não é necessário se você não usar eventos numéricos ou de moeda na variável `products`.

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
    * Action Type: Initialize addProductEvent
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
/* Adobe Consulting Plugin: addProductEvent v2.0 */
function addProductEvent(en,ev,ap){var f=en,g=ev,c=ap;if("-v"===f)return{plugin:"addProductEvent",version:"2.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,e;b<window.s_c_il.length;b++)if(e=window.s_c_il[b],e._c&&"s_c"===e._c)return e}();if("undefined"!==typeof d&&(d.contextData.addProductEvent="2.0",window.apl=window.apl||function(b,e,c,d,f){function g(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!b||"string"===typeof b){if("string"!==typeof e||""===e)return b;c=c||",";d=d||c;1==d&&(d=c,f||(f=1));2==d&&1!=f&&(d=c);e=e.split(",");k=e.length;for(var h=0;h<k;h++)g(b,e[h],c,f)||(b=b?b+d+e[h]:e[h])}return b},"string"===typeof f))if(g=isNaN(g)?"1":String(g),c=c||!1,d.events=window.apl(d.events,f),d.products){var l=d.products.split(","),m=l.length;c=c?0:m-1;for(var b;c<m;c++)b=l[c].split(";"),b[4]&&-1<b[4].indexOf("event")?b[4]=b[4]+"|"+f+"="+g:b[5]?b[4]=f+"="+g:b[4]||(b[3]||(b[3]=""),b[2]||(b[2]=""),b[1]||(b[1]=""),b[4]=f+"="+g),l[c]=b.join(";");d.products=l.join(",")}else d.products=";;;;"+f+"="+g};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `addProductEvent` usa os seguintes argumentos:

* **`en`** (obrigatório, string): o evento a ser adicionado à última entrada na variável `products`. Se a variável `products` estiver vazia, uma entrada de produto &quot;em branco&quot; será criada com o evento (e seu valor) anexado.
* **`ev`** (obrigatório, string): o valor atribuído ao evento numérico ou de moeda no argumento `en`.  O valor padrão é `1` quando um valor não está definido. Os números não expressos em aspas de string também são válidos.
* **`ap`** (opcional, booleano): se a variável products contiver mais de uma entrada de produto no momento, um valor `true` (ou `1`) fará o evento ser adicionado a todas as entradas de produto.  O valor padrão é `false` quando um valor não está definido.

`addProductEvent` não tem retorno. Em vez disso, ele adiciona o evento e seu valor à variável `products`. O plug-in também adiciona automaticamente o evento à variável [`events`](../page-vars/events/events-overview.md), já que ele também é necessário.

## Cookies

A função `addProductEvent` não cria ou usa cookies.

## Exemplos

```js
// Sets the products variable to ";product1;3;300,;product2;2;122,;product3;1;25;event35=25".
// Also sets the events variable to "purchase,event35".
s.products = ";product1;3;300,;product2;2;122,;product3;1;25";
s.events = "purchase";
addProductEvent("event35", "25");

// Sets the products variable to ";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25".
s.products = ";product1;3;300,;product2;2;122,;product3;1;25";
addProductEvent("event35", 25, true);

// Sets the products variable to ";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"
// Also sets the s.events variable to "purchase,event2,event33,event34,event35".
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
addProductEvent("event33", "12");
addProductEvent("event34", "10");
addProductEvent("event35", "15");

// Sets the products variable to ";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15".
// Also sets the events variable to "purchase,event2,event33,event34,event35".
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
addProductEvent("event33", "12", 1);
addProductEvent("event34", 10, 1);
addProductEvent("event35", "15", 1);

// If the products variable isn't already set, sets it to ";;;;event35=25".
// Also appends event35 to the events variable.
addProductEvent("event35", "25");
```

## Histórico da versão

### 2.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 1.0 (7 de outubro, 2019)

* Versão inicial.
