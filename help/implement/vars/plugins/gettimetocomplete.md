---
title: getTimeToComplete
description: Meça o tempo gasto para concluir uma tarefa.
feature: Appmeasurement Implementation
exl-id: 90a93480-3812-49d4-96f0-8eaf5a70ce3c
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 89%

---

# Plug-in da Adobe: getTimeToComplete

{{plug-in}}

O plug-in `getTimeToComplete` rastreia o tempo que um usuário leva para concluir um processo em um site. O &quot;relógio&quot; começa quando a ação `start` é chamada e termina quando a ação `stop` é chamada. A Adobe recomenda usar esse plug-in se houver um fluxo de trabalho no site que demore algum tempo para ser concluído e você quiser saber quanto tempo os visitantes levam para concluí-lo. Não é necessário usar esse plug-in se o fluxo de trabalho do site levar um curto período de tempo (menos de 3 segundos), pois a granularidade chega a, no mínimo, um segundo completo.

## Instale o plug-in usando a extensão Web SDK ou Web SDK

Este plug-in ainda não é compatível com o Web SDK.

## Instale o plug-in usando a extensão Adobe Analytics.

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo].
1. Instale e publique a extensão [!UICONTROL Plug-ins comuns do Analytics].
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar getTimeToComplete
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do

Se você não quiser usar a extensão de plug-in de plug-ins comuns do Analytics, poderá usar o editor de código personalizado.

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
/* Adobe Consulting Plugin: getTimeToComplete v4.0 */
function getTimeToComplete(sos,cn,exp,tp){var f=sos,m=cn,l=exp,e=tp;if("-v"===f)return{plugin:"getTimeToComplete",version:"4.0"};var k=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof k&&(k.contextData.getTimeToComplete="4.0");window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var h="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,h="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,h="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,h="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,h="seconds",d=isNaN(d)?.2:b/d);h=Math.round(c*d/b)/d+" "+h;0===h.indexOf("1 ")&&(h=h.substring(0,h.length-1));return h}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var e=window.location.hostname,h=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){h=2<h?h:2;var f=e.lastIndexOf(".");if(0<=f){for(;0<=f&&1<h;)f=e.lastIndexOf(".",f-1),h--;f=0<f?e.substring(f):e}}g=f;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""};f=f?f.toLowerCase():"start";if("stop"===f||"start"===f){m=m?m:"s_gttc";e?e="d"===e?864E5:"h"===e?36E5:"s"===e?1E3:6E4:(l=30,e=6E4);l=isNaN(l)?30:l;l*=e;k=cookieRead(m);e=new Date;if("stop"===f&&k)return l=Math.round((e.getTime()-k)/1E3),cookieWrite(m,"",0),formatTime(l);"start"!==f||k?k&&Number(k)<e.getTime()+18E5&&cookieWrite(m,k,30):(f=String(e.getTime()),e.setTime(e.getTime()+l),cookieWrite(m,f,e))}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getTimeToComplete` usa os seguintes argumentos:

* **`sos`** (opcional, string): defina como `"start"` quando quiser iniciar o cronômetro. Defina como `"stop"` quando quiser parar o cronômetro. O padrão é `"start"`.
* **`cn`** (opcional, string): o nome do cookie que armazenará o tempo inicial. O padrão é `"s_gttc"`.
* **`exp`** (opcional, número inteiro): o número de segundos, horas ou dias (dependendo do argumento `tp` de separação de tempo) em que o cookie (e o cronômetro) expira. O padrão é 30 minutos.
* **`tp`** (opcional, string): a string de separação de tempo em que o cookie (e o cronômetro) expira, usada com o argumento `exp`. Defina como “d” para dias, “h” para horas ou “s” para segundos. Se isso não for definido, a expiração do cookie (e do cronômetro) é de 30 minutos, independentemente do valor do argumento `exp` estar definido.

Chamar essa função retorna uma string que contém o número de dias, horas, minutos e/ou segundos decorridos entre a ação `"start"` e a ação `"stop"`.

## Exemplos

```js
// Start the timer when the visitor starts the checkout
if(s.events.indexOf("scCheckout") > -1) getTimeToComplete("start");

// Stop the timer when the visitor makes the purchase and set prop1 to the time difference between stop and start
// Sets prop1 to the amount of time it took to complete the purchase process
if(s.events.indexOf("purchase") > -1) s.prop1 = getTimeToComplete("stop");

// Simultaneously track the time it takes to complete a purchase and to fill out a registration form
// Stores each timer in their own respective cookies so they run independently
if(inList(s.events, "scCheckout")) getTimeToComplete("start", "gttcpurchase");
if(inList(s.events, "purchase")) s.prop1 = getTimeToComplete("start", "gttcpurchase");
if(inList(s.events, "event1")) getTimeToComplete("start", "gttcregister", 7, "d");
if(inList(s.events, "event2")) s.prop2 = getTimeToComplete("stop", "gttcregister", 7, "d");
```

## Histórico da versão

### 4.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 3.1 (30 de setembro de 2019)

* Foi adicionada uma lógica que requer um valor &quot;start&quot; ou &quot;stop&quot; no primeiro argumento.  Todos os outros valores passados impedem a execução do plug-in.
* Atualização do plug-in `inList 2.0` para `inList 2.1`.

### 3.0 (23 de agosto de 2018)

* Atualização do plug-in `formatTime v1.0` para `formatTime v1.1`.

### 3.0 (17 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código).
* Correção de erros secundários.

### 2.0 (21 de junho de 2016)

* Eliminação da dependência do plug-in `p_fo`.
* Compatibilidade adicionada com o H-code e o AppMeasurement.
* Adicionado o registro de log do console.
