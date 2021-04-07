---
title: getTimeToComplete
description: Meça o tempo gasto para concluir uma tarefa.
translation-type: ht
source-git-commit: 37a3a44053260d9cdb2a3797e07f6d34592abc1f
workflow-type: ht
source-wordcount: '762'
ht-degree: 100%

---


# Plug-in da Adobe: getTimeToComplete

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getTimeToComplete` rastreia o tempo que um usuário leva para concluir um processo em um site. O &quot;relógio&quot; começa quando a ação `start` é chamada e termina quando a ação `stop` é chamada. A Adobe recomenda usar esse plug-in se houver um fluxo de trabalho no site que demore algum tempo para ser concluído e você quiser saber quanto tempo os visitantes levam para concluí-lo. Não é necessário usar esse plug-in se o fluxo de trabalho do site levar um curto período de tempo (menos de 3 segundos), pois a granularidade chega a, no mínimo, um segundo completo.

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
   * Tipo de ação: inicializar getTimeToComplete
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
/* Adobe Consulting Plugin: getTimeToComplete v4.0 */
function getTimeToComplete(sos,cn,exp,tp){var f=sos,m=cn,l=exp,e=tp;if("-v"===f)return{plugin:"getTimeToComplete",version:"4.0"};var k=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof k&&(k.contextData.getTimeToComplete="4.0");window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var h="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,h="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,h="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,h="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,h="seconds",d=isNaN(d)?.2:b/d);h=Math.round(c*d/b)/d+" "+h;0===h.indexOf("1 ")&&(h=h.substring(0,h.length-1));return h}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var e=window.location.hostname,h=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){h=2<h?h:2;var f=e.lastIndexOf(".");if(0<=f){for(;0<=f&&1<h;)f=e.lastIndexOf(".",f-1),h--;f=0<f?e.substring(f):e}}g=f;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""};f=f?f.toLowerCase():"start";if("stop"===f||"start"===f){m=m?m:"s_gttc";e?e="d"===e?864E5:"h"===e?36E5:"s"===e?1E3:6E4:(l=30,e=6E4);l=isNaN(l)?30:l;l*=e;k=cookieRead(m);e=new Date;if("stop"===f&&k)return l=Math.round((e.getTime()-k)/1E3),cookieWrite(m,"",0),formatTime(l);"start"!==f||k?k&&Number(k)<e.getTime()+18E5&&cookieWrite(m,k,30):(f=String(e.getTime()),e.setTime(e.getTime()+l),cookieWrite(m,f,e))}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getTimeToComplete` aceita os seguintes argumentos:

* **`sos`** (opcional, string): defina como `"start"` quando quiser iniciar o cronômetro. Defina como `"stop"` quando quiser parar o cronômetro. O padrão é `"start"`.
* **`cn`** (opcional, string): o nome do cookie que armazenará o tempo inicial. O padrão é `"s_gttc"`.
* **`exp`** (opcional, número inteiro): o número de dias que dura o cookie (e o cronômetro). O padrão é `0`, que representa o fim da sessão do navegador.

Chamar esse método retorna uma string que contém o número de dias, horas, minutos e/ou segundos decorridos entre a ação `"start"` e a ação `"stop"`.

## Exemplos de chamadas

### Exemplo #1

Use essas chamadas para determinar o tempo decorrido entre o momento em que um visitante inicia o processo de finalização e o momento em que realiza uma compra.

Inicie o cronômetro quando o visitante iniciar a finalização:

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Pare o cronômetro quando o visitante fizer a compra e defina prop1 como a diferença de tempo entre a parada e o início:

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 capturará o tempo necessário para concluir o processo de compra

### Exemplo #2

Se você quiser ter vários cronômetros em execução ao mesmo tempo (para medir processos diferentes), será necessário definir manualmente o argumento de cookie cn.  Por exemplo, se você quiser medir a quantidade de tempo necessária para que uma compra seja concluída, defina o código a seguir...

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

... mas se você também quiser medir (ao mesmo tempo) o tempo necessário para preencher um formulário de inscrição, execute também seguinte código:

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

No segundo exemplo, event1 deve capturar o início de um processo de registro que pode levar até 7 dias para ser concluído (por qualquer motivo), e event2 deve capturar a conclusão do registro.  s.prop2 capturará o tempo necessário para concluir o processo de registro

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
