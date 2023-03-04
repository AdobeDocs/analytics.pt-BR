---
title: getVisitNum
description: Rastreia o número da visita atual de um visitante.
feature: Variables
exl-id: 05b3f57c-7268-4585-a01e-583f462ff8df
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 100%

---

# Plug-in da Adobe: getVisitNum

{{plug-in}}

O plug-in `getVisitNum` retorna o número da visita para todos os visitantes que chegam ao site dentro do número desejado de dias. O Analysis Workspace oferece uma dimensão &quot;Número de visitas&quot; que fornece funcionalidade semelhante. A Adobe recomenda usar esse plug-in se você quiser mais controle sobre como o número de visitas é incrementado. Esse plug-in é desnecessário se a dimensão &quot;Número de visitas&quot; integrada no Analysis Workspace for suficiente para suas necessidades de relatórios.

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
    * Action Type: Initialize getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.2 */
function getVisitNum(rp,erp){var a=rp,l=erp;function m(c){return isNaN(c)?!1:(parseFloat(c)|0)===parseFloat(c)}function n(c){var b=new Date,e=isNaN(c)?0:Math.floor(c);b.setHours(23);b.setMinutes(59);b.setSeconds(59);"w"===c&&(e=6-b.getDay());if("m"===c){e=b.getMonth()+1;var a=b.getFullYear();e=(new Date(a?a:1970,e?e:1,0)).getDate()-b.getDate()}b.setDate(b.getDate()+e);"y"===c&&(b.setMonth(11),b.setDate(31));return b}if("-v"===a)return{plugin:"getVisitNum",version:"4.2"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof f&&(f.contextData.getVisitNum="4.2");window.cookieWrite=window.cookieWrite||function(c,b,e){if("string"===typeof c){var a=window.location.hostname,d=window.location.hostname.split(".").length-1;if(a&&!/^[0-9.]+$/.test(a)){d=2<d?d:2;var h=a.lastIndexOf(".");if(0<=h){for(;0<=h&&1<d;)h=a.lastIndexOf(".",h-1),d--;h=0<h?a.substring(h):a}}g=h;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var f=new Date;f.setTime(f.getTime()+6E4*e)}else f=e;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:365;l="undefined"!==typeof l?!!l:m(a)?!0:!1;var p=(new Date).getTime();f=n(a);if(window.cookieRead("s_vnc"+a))var d=window.cookieRead("s_vnc"+a).split("&vn="),k=d[1];if(window.cookieRead("s_ivc"))return k?(window.cookieWrite("s_ivc",!0,30),k):"unknown visit number";if("undefined"!==typeof k)return k++,d=l&&m(a)?p+864E5*a:d[0],f.setTime(d),window.cookieWrite("s_vnc"+a,d+"&vn="+k,f),window.cookieWrite("s_ivc",!0,30),k;d=m(a)?p+864E5*a:n(a).getTime();window.cookieWrite("s_vnc"+a,d+"&vn=1",f);window.cookieWrite("s_ivc",!0,30);return"1"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getVisitNum` usa os seguintes argumentos:

* **`rp`** (opcional, número inteiro OU string): o número de dias antes da redefinição do contador do número de visitas.  O valor padrão é `365` quando um valor não está definido.
   * Quando esse argumento é `"w"`, o contador é reiniciado no final da semana (neste sábado, às 23:59)
   * Quando esse argumento é `"m"`, o contador é redefinido no final do mês (o último dia deste mês)
   * Quando esse argumento é `"y"`, o contador é reiniciado no final do ano (31 de dezembro)
* **`erp`** (opcional, booleano): Quando o argumento `rp` é um número, esse argumento determina se a expiração do número de visitas deve ser estendida. Se definido como `true`, as ocorrências subsequentes do site redefinirão o contador de número de visitas. Se definido como `false`, as ocorrências subsequentes do site serão estendidas quando o contador de número de visitas é redefinido. O padrão é `true`. Esse argumento não é válido quando o argumento `rp` é uma string.

O número de visitas aumenta sempre que o visitante retorna ao site após 30 minutos de inatividade. A chamada dessa função retorna um número inteiro que representa o número de visita atual do visitante.

Este plug-in define um cookie próprio chamado `"s_vnc[LENGTH]"`, onde `[LENGTH]` é o valor transmitido para o argumento `rp`. Por exemplo, `"s_vncw"`, `"s_vncm"` ou `"s_vnc365"`. O valor do cookie é uma combinação de um carimbo de data e hora de Unix que representa o momento quando o contador de visitas é redefinido, como um fim da semana, fim do mês ou após 365 dias de inatividade. Também contém o número de visitas atual. Este plug-in define outro cookie chamado `"s_ivc"`, que está definido como `true` e expira após 30 minutos de inatividade.

## Exemplos

```js
// Sets prop4 to the visit number, storing the value in a cookie that expires in 365 days
// The cookie value is reset only if there are 365+ days of inactivity or the visitor clears their cookies.
s.prop4 = getVisitNum();

// Sets eVar4 to the visit number, storing the value in a cookie that expires in 200 days
// The cookie value is reset only if there are 200+ days of inactivity or the visitor clears their cookies.
s.eVar4 = getVisitNum(200);

// Sets eVar16 to the visit number, storing the value in a cookie that expires in 90 days.
// The cookie value is reset after 90 days, regardless of how many visits that happen in those 90 days.
s.eVar16 = getVisitNum(90,false);

// Track the visit number unique to the week, month, and year, all in separate variables
// The plug-in automatically creates three separate cookies to track these values
s.prop1 = getVisitNum("w");
s.prop2 = getVisitNum("m");
s.prop3 = getVisitNum("y");
```

## Histórico da versão

### 4.2 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 4.11 (30 de setembro de 2019)

* Correção de um problema em que o argumento `erp` era explicitamente definido como `false`.

### 4.1 (21 de maio de 2018)

* Atualização do plug-in `endOfDatePeriod` para v1.1.

### 4.0 (17 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código).
* Argumentos de cookie removidos, pois o plug-in agora gera cookies dinamicamente com base no argumento `rp`).

### 3.0 (5 de junho de 2016)

* Reformulação completa.
* Combinadas todas as soluções anteriores disponíveis em várias versões do plug-in `getVisitNum`.
