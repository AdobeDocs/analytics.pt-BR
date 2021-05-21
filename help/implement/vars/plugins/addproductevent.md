---
title: addProductEvent
description: Adiciona eventos personalizados às variáveis products e events.
exl-id: 74f4cb93-714a-4d2b-88f3-408d032f6811
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '632'
ht-degree: 100%

---

# Plug-in da Adobe: addProductEvent

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `addProductEvent` adiciona um evento numérico ou de moeda à variável [`products`](../page-vars/products.md). A Adobe recomenda usar esse plug-in se você quiser adicionar um evento numérico ou de moeda à variável `products` sem se preocupar com o formato da string do produto. Esse plug-in não é necessário se você não usar eventos numéricos ou de moeda na variável `products`.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo].
1. Instale e publique a extensão [!UICONTROL Plug-ins comuns do Analytics].
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar addProductEvent
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do Launch

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
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

O método `addProductEvent` aceita os seguintes argumentos:

* **`en`** (obrigatório, string): o evento a ser adicionado à última entrada na variável `products`. Se a variável `products` estiver vazia, uma entrada de produto &quot;em branco&quot; será criada com o evento (e seu valor) anexado.
* **`ev`** (obrigatório, string): o valor atribuído ao evento numérico ou de moeda no argumento `en`.  O valor padrão é `1` quando um valor não está definido.
* **`ap`** (opcional, booleano): se a variável products contiver mais de uma entrada de produto no momento, um valor `true` (ou `1`) fará o evento ser adicionado a todas as entradas de produto.  O valor padrão é `false` quando um valor não está definido.

`addProductEvent` não tem retorno. Em vez disso, ele adiciona o evento e seu valor à variável `products`. O plug-in também adiciona automaticamente o evento à variável [`events`](../page-vars/events/events-overview.md), já que ele também é necessário.

## Cookies

O plug-in addProductEvent não cria ou usa cookies.

## Exemplos de chamadas

### Exemplo #1

O código a seguir define a variável `s.products` como `";product1;3;300,;product2;2;122,;product3;1;25;event35=25"`.

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25"
s.events="purchase";
s.addProductEvent("event35", "25");
```

O código acima também define a variável `s.events` como `"purchase,event35"`

### Exemplo #2

O código a seguir define a variável `s.products` como `";product1;3;300;event35=25,;product2;2;122;event35=25,;product3;1;25;event35=25"`

```js
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
s.addProductEvent("event35", 25, 1);
```

Quando o terceiro argumento na chamada `addProductEvent` for `true` (ou `1`), cada entrada de produto tem o evento especificado na chamada adicionado ao seu valor.

### Exemplo #3

O código a seguir define a variável `s.products` como `";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25;event33= 12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25";
s.events="purchase,event2";
s.addProductEvent("event33", "12");
s.addProductEvent("event34", "10");
s.addProductEvent("event35", "15");
```

O código acima também define a variável `s.events` como `"purchase,event2,event33,event34,event35"`

### Exemplo #4

O código a seguir define a variável `s.products` como `";product1;3;300;event2=10|event33=12|event34=10|event35=15;eVar33=large|eVar34=men|eVar35=blue, ;product2;2;122;event33=12|event34=10|event35=15,;product3;1;25;event33=12|event34=10|event35=15"`

```js
s.products=";product1;3;300;event2=10;eVar33=large|eVar34=men|eVar35=blue,;product2;2;122,;product3;1;25"
s.events="purchase,event2"
s.addProductEvent("event33", "12", 1);
s.addProductEvent("event34", 10, 1);
s.addProductEvent("event35", "15", 1);
```

O código acima também define a variável `s.events` como `"purchase,event2,event33,event34,event35"`.

>[!NOTE]
>
>O segundo argumento na chamada pode ser um número inteiro **ou** uma string que representa um número inteiro

### Exemplo #5

Se o `s.products` ainda não estiver definido, o código a seguir o define como `";;;;event35=25"`

```js
s.addProductEvent("event35", "25");
```

O código acima também anexa o `"event35"` ao final do `s.events` **ou**, se o `s.events` ainda não estiver definido, o código acima define o `s.events` como `"event35"`

## Histórico da versão

### 2.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 1.0 (7 de outubro, 2019)

* Versão inicial.
