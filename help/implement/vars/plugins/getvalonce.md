---
title: getValOnce
description: Impeça que uma variável do Analytics seja definida com o mesmo valor duas vezes seguidas.
feature: Variables
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 98%

---

# Plug-in da Adobe: getValOnce

{{plug-in}}

O plug-in `getValOnce` impede que uma variável seja definida com o mesmo valor mais de uma vez. A Adobe recomenda usar esse plug-in quando você deseja desduplicar ocorrências nas quais um visitante atualiza uma página ou visita uma determinada página várias vezes. Esse plug-in é desnecessário se você não se preocupar com a métrica &quot;Ocorrências&quot; no Analysis Workspace.

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
    * Action Type: Initialize getValOnce
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
/* Adobe Consulting Plugin: getValOnce v3.1 */
function getValOnce(vtc,cn,et,ep){var e=vtc,i=cn,t=et,n=ep;  if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.1"};var o=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();if(void 0!==o&&(o.contextData.getValOnce="3.1"),window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){var n=window.location.hostname,o=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){o=2<o?o:2;var r=n.lastIndexOf(".");if(0<=r){for(;0<=r&&1<o;)r=n.lastIndexOf(".",r-1),o--;r=0<r?n.substring(r):n}}if(g=r,i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var f=new Date;f.setTime(f.getTime()+6e4*t)}else f=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!=typeof cookieRead)&&cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),n=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>n?i.length:n)))?e:""},e){var i=i||"s_gvo",t=t||0,n="m"===n?6e4:864e5;if(e!==cookieRead(i)){var r=new Date;return r.setTime(r.getTime()+t*n),cookieWrite(i,e,0===t?0:r),e}}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getValOnce` usa os seguintes argumentos:

* **`vtc`** (obrigatório, string): a variável cujo valor será verificado para conferir se já teve anteriormente um valor idêntico
* **`cn`** (opcional, string): o nome do cookie que contém o valor a ser verificado. O padrão é `"s_gvo"`
* **`et`** (opcional, número inteiro): a validade do cookie em dias (ou minutos, dependendo do argumento `ep`). O padrão é `0`, que expira no final da sessão do navegador
* **`ep`** (opcional, string): somente defina esse argumento se o argumento `et` também estiver definido. Configure esse argumento como `"m"` se desejar que o argumento `et` expire em minutos em vez de dias. O padrão é `"d"`, que define o argumento `et` para dias.

Se o argumento `vtc` e o valor do cookie corresponderem um ao outro, essa função retornará uma string vazia. Se o argumento `vtc` e o valor do cookie não corresponderem um ao outro, a função retornará o argumento `vtc` como uma string.

## Exemplos

```js
// Prevent the same value from being passed in to the campaign variable more than once in a row for next 30 days
s.campaign = getValOnce(s.campaign,"s_campaign",30);

// Prevent the same value from being passed in to eVar2 more than once in a row for the browser session
s.eVar2 = getValOnce(s.eVar2,"s_ev2");

// Prevent the same value from being passed in to eVar8 more than once in a row for 10 minutes
s.eVar8 = getValOnce(s.eVar8,"s_ev8",10,"m");
```

## Histórico da versão

### 3.1 (22 de setembro de 2022)

* Correção de um erro de expiração

### 3.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 2,01

* Correção de um problema com a gravação de cookies.

### 2.0

* Versão pontual (recompilada, menor tamanho de código).

### 1.1

* Adicionada a opção de escolher minutos ou dias para a expiração por meio do parâmetro `t`.
* Corrigido o escopo da variável `k` usada para restringi-la somente ao plug-in. Essa alteração evita possíveis interferências com outros códigos na página.
