---
title: ' addProductEvent'
description: Adiciona eventos personalizados à variável products e events.
translation-type: tm+mt
source-git-commit: 7a455fb9eb355617bab016218b171dffa8d21958

---


# Plug-in da Adobe: addProductEvent

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O plug- `addProductEvent` -in adiciona um evento numérico ou de moeda à `products` variável. A Adobe recomenda usar esse plug-in se você quiser adicionar um evento numérico ou de moeda à `products` variável sem se preocupar com o formato da string do produto. Esse plug-in não é necessário se você não usar eventos numéricos ou de moeda na `products` variável.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Catalog] botão
1. Instalar e publicar a [!UICONTROL Common Analytics Plugins] extensão
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhum
   * Evento: Principal - Biblioteca carregada (início da página)
1. Adicione uma ação à regra acima com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar addProductEvent
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado Iniciar

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão na extensão do Adobe Analytics.
1. Amplie o [!UICONTROL Configure tracking using custom code] acordeão, que revela o [!UICONTROL Open Editor] botão.
1. Abra o editor de código personalizado e cole o código do plug-in fornecido abaixo na janela de edição.
1. Salve e publique as alterações na extensão do Analytics.

## Instale o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando `s_gi`). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvent v1.0 (Requires apl v3.1 and inList v2.0+ plug-ins) */
s.addProductEvent=function(en,ev,ap){var s=this;if("string"===typeof en)if(ev=isNaN(ev)?"1":String(ev),ap=ap||!1,s.events= s.apl(s.events,en),s.products){var e=s.products.split(",");ap=ap?0:e.length-1;for(var a;ap<e.length;ap++)a=e[ap].split(";") ,a[4]&&a[4].includes("event")?a[4]=a[4]+"|"+en+"="+ev:a[5]?a[4]=en+"="+ev:a[4]||(a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[4]=en+"="+ev),e[ap]=a.join(";");s.products=e.join(",")}else s.products=";;;;"+en+"="+ev};

/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `addProductEvent` método usa os seguintes argumentos:

* **`en`** (obrigatório, string): O evento a ser adicionado à última entrada na `products` variável. Se a `products` variável estiver vazia, uma entrada de produto &quot;em branco&quot; será criada com o evento (e seu valor) anexado.
* **`ev`** (obrigatório, string): O valor atribuído ao evento numérico ou de moeda no `en` argumento.  O padrão é `1` quando não está definido.
* **`ap`** (opcional, booleano): Se a variável products contiver mais de uma entrada de produto no momento, um valor de `true` (ou `1`) adicionará o evento a todas as entradas de produto.  O padrão é `false` quando não está definido.

Não `addProductEvent` retorna nada. Em vez disso, adiciona o evento e seu valor à `products` variável. O plug-in também adiciona automaticamente o evento à `events` variável, já que também é necessário.

## Cookies

O plug-in addProductEvent não cria ou usa cookies

## Exemplos de chamadas

### Exemplo nº 1

O código a seguir define a `s.products` variável como `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`.

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

O código acima também define a `s.events` variável como `"purchase,event35"`

### Exemplo nº 2

O código a seguir define a `s.products` variável como `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

Quando o terceiro argumento na `addProductEvent` chamada é `true` (ou `1`), cada entrada de produto tem o evento especificado na chamada adicionado ao seu valor.

### Exemplo 3

O código a seguir define a `s.products` variável como `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

O código acima também define a `s.events` variável como `"purchase,event2,event33,event34,event35"`

### Exemplo nº 4

O código a seguir define a `s.products` variável como `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

O código acima também define a `s.events` variável como `"purchase,event2,event33,event34,event35"`.

> [!NOTE] O segundo argumento na chamada pode ser um número inteiro **ou** uma string que representa um número inteiro

### Exemplo nº 5

Se ainda `s.products` não estiver definido, o código a seguir o define como `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

O código acima também anexa `"event35"` ao final do `s.events` ou **, se** ainda não estiver definido, o código acima define `s.events` `s.events` como `"event35"`

## Histórico da versão

### 1.0 (7 de outubro de 2019)

* Versão inicial.
