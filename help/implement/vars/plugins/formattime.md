---
title: formatTime
description: Converta um número de segundos para seu equivalente em minutos, horas etc.
feature: Appmeasurement Implementation
exl-id: 4b98e7fe-f05b-4346-b284-697268adc1a2
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 88%

---

# Plug-in da Adobe: formatTime

{{plug-in}}

O plug-in `formatTime` permite que você trate qualquer número de segundos e o apresente em um formato reduzido, arredondado para um valor referencial desejado. A Adobe recomenda usar esse plug-in se você quiser capturar um valor de tempo em segundos e convertê-lo em um formato simplificado (como minutos, dias ou semanas). Esse plug-in é desnecessário se você não quiser agrupar valores com em segundos em um formato arredondado por tempo.

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
   * Tipo de ação: inicializar formatTime
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
/* Adobe Consulting Plugin: formatTime v2.0 */
function formatTime(ns,tf,bml){var f=ns,d=tf,e=bml;function h(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(arguments&&"-v"===arguments[0])return{plugin:"formatTime",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.formatTime="2.0");if(!("undefined"===typeof f||isNaN(f)||0>Number(f))){b="";if("string"===typeof d&&"d"===d||("string"!==typeof d||!h("h,m,s",d))&&86400<=f){var c=86400;var g="days";b=isNaN(e)?1:c/(e*c)}else"string"===typeof d&&"h"===d||("string"!==typeof d||!h("m,s",d))&&3600<=f?(c=3600,g="hours",b=isNaN(e)?4:c/(e*c)):"string"===typeof d&&"m"===d||("string"!==typeof d||!h("s",d))&&60<=f?(c=60,g="minutes",b=isNaN(e)?2:c/(e*c)):(c=1,g="seconds",b=isNaN(e)?.2:c/e);b=Math.round(f*b/c)/b+" "+g;0===b.indexOf("1 ")&&(b=b.substring(0,b.length-1));return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `formatTime` usa os seguintes argumentos:

* **`ns`** (obrigatório, número inteiro): o número de segundos a ser convertido ou formatado
* **`tf`** (opcional, string): o tipo de formato em que os segundos devem ser retornados; o padrão é segundos
   * Defina como `"d"` se desejar tempo em dias (arredondado para o referencial de 1/4 de dia que estiver mais próximo, por padrão)
   * Defina como `"h"` se desejar tempo em horas (arredondado para o referencial de 1/4 de hora que estiver mais próximo, por padrão)
   * Defina como `"m"` se desejar tempo em minutos (arredondado para o referencial de 1/2 minuto que estiver mais próximo, por padrão)
   * Defina como `"s"` se desejar tempo em segundos (arredondado para o referencial de 5 segundos que estiver mais próximo, por padrão)
* **`bml`** (opcional, número): a quantidade de tempo dos referenciais de arredondamento. Padrões para os referenciais listados no argumento `tf`

A função retorna o número de segundos formatados usando a unidade especificada no argumento `tf`. Se o argumento `tf` não estiver definido:

* Qualquer coisa menor que um minuto é arredondada para o referencial de 5 segundos que estiver mais próximo
* Qualquer coisa entre um minuto e uma hora é arredondada para o referencial de 1/2 minuto que estiver mais próximo
* Qualquer coisa entre uma hora e um dia é arredondada para o referencial de 1/4 de hora que estiver mais próximo
* Qualquer coisa maior que um dia é arredondada para o valor referencial de dia que estiver mais próximo

## Exemplos

```js
// Sets eVar1 to "10.5 hours".
// 38242 seconds equals 10 hours, 37 minutes, and 22 seconds. Since the tf argument is not set, the value returned is the number of seconds converted to the nearest quarter-hour benchmark.
s.eVar1 = formatTime(38242);

// Sets eVar4 to "10.75 hours".
// 38250 seconds equals 10 hours, 37 minutes, and 30 seconds. This value rounds up to the nearest quarter hour.
s.eVar4 = formatTime(38250);

// Sets eVar9 to "637.5 minutes".
s.eVar9 = formatTime(38242, "m");

// Sets eVar14 to "640 minutes".
// The tf argument forces the returned value to minutes, while the bml argument forces the value to the nearest 20-minute increment.
s.eVar14 = formatTime(38242, "m", 20);

// Sets eVar2 to "126 seconds", the closest 2-second benchmark to 125 seconds.
s.eVar2 = formatTime(125, "s", 2);

// Sets eVar7 to "3 minutes", the closest 3-minute benchmark to 125 seconds.
s.eVar7 = formatTime(125, "m", 3);

// Sets eVar55 to "2.4 minutes, the closest 2/5-minute benchmark to 145 seconds.
s.eVar55 = formatTime(145, "m", .4);
```

## Histórico da versão

### 2.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 1.1 (21 de maio de 2018)

* Adição do argumento `bml` para permitir mais flexibilidade no arredondamento

### 1.0 (15 de abril de 2018)

* Versão inicial.
