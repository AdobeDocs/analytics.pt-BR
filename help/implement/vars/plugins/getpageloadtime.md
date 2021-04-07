---
title: getPageLoadTime
description: Rastreie o tempo que uma página leva para ser carregada.
translation-type: ht
source-git-commit: b3c5fa41194d74725f48e12a546d8ce1c08b9b7d
workflow-type: ht
source-wordcount: '566'
ht-degree: 100%

---


# Plug-in da Adobe: getPageLoadTime

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getPageLoadTime` usa o objeto de desempenho JavaScript para permitir que você meça a quantidade de tempo que uma página leva para carregar completamente. A Adobe recomenda usar esse plug-in se você quiser medir quanto tempo as páginas levam para serem carregadas.

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
   * Tipo de ação: inicializar getPageLoadTime
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
/* Adobe Consulting Plugin: getPageLoadTime v2.0 with performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (Requires AppMeasurement and the p_fo plugin) */
function getPageLoadTime(){function f(){function a(a,b){if(0<=a&&0<=b)return 6E4>a-b&&0<=a-b?parseFloat((a-b)/1E3).toFixed(2):60}var b=performance.timing;0<b.loadEventEnd&&(clearInterval(window.pi),""===window.cookieRead("s_plt")&&(window.cookieWrite("s_plt",a(b.loadEventEnd,b.navigationStart)),window.cookieWrite("s_pltp",window.pageName)));window.ptc=b.loadEventEnd}if(arguments&&"-v"===arguments[0])return{plugin:"getPageLoadTime",version:"2.0"};var c=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof c&&(c.contextData.getPageLoadTime="2.0");window.pageName="undefined"!==typeof c&&c.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,e){if("string"===typeof a){var c=window.location.hostname,h=window.location.hostname.split(".").length-1;if(c&&!/^[0-9.]+$/.test(c)){h=2<h?h:2;var d=c.lastIndexOf(".");if(0<=d){for(;0<=d&&1<h;)d=c.lastIndexOf(".",d-1),h--;d=0<d?c.substring(d):c}}g=d;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var k=new Date;k.setTime(k.getTime()+6E4*e)}else k=e;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),f=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>f?b.length:f)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};"undefined"!==typeof performance&&p_fo("performance")&&((c=performance,c.clearResourceTimings(),""!==window.cookieRead("s_plt")&&(0<c.timing.loadEventEnd&&clearInterval(window.pi),window._pltLoadTime=window.cookieRead("s_plt"),window._pltPreviousPage=window.cookieRead("s_pltp"),window.cookieWrite("s_plt",""),window.cookieWrite("s_pltp","")),0===c.timing.loadEventEnd)?window.pi=setInterval(function(){f()},250):0<c.timing.loadEventEnd&&(window.ptc?window.ptc===c.timing.loadEventEnd&&1===c.getEntries().length&&(window.pwp=setInterval(function(){var a=performance;0<a.getEntries().length&&(window.ppfe===a.getEntries().length?clearInterval(window.pwp):window.ppfe=a.getEntries().length);""===window.cookieRead("s_plt")&&(window.cookieWrite("s_plt",((a.getEntries()[a.getEntries().length-1].responseEnd-a.getEntries()[0].startTime)/1E3).toFixed(2)),window.cookieWrite("s_pltp",window.pageName))},500)):f()))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getPageLoadTime` não usa nenhum argumento. Quando você chama esse método, ele não retorna nada. Em vez disso, ele define as seguintes variáveis:

* `s._pltPreviousPage`: a página anterior, para que seja possível correlacioná-la ao tempo de carregamento.
* `s._pltLoadTime`: o tempo em segundos que demorou para a página anterior ser carregada.

O plug-in getPageLoadTime cria dois cookies próprios:

* `s_plt`: o tempo em segundos que demorou para a página anterior ser carregada. Expira no final da sessão do navegador.
* `s_pltp` O valor da variável `s.pageName` conforme registrado na solicitação de imagem anterior do Adobe Analytics. Expira no final da sessão do navegador.

## Exemplos de chamadas

### Exemplo #1

Executar o código a seguir...

```js
if(s.pageName) s.getPageLoadTime();
if(s._pltPreviousPage)
{
  s.prop10 = s._pltLoadTime;
  s.prop11 = s._pltPreviousPage
  s.eVar10 = prop11;
  s.events = "event100=" + s._pltLoadTime;
}
```

... terá o seguinte resultado:

* Execute o plug-in getPageLoadTime quando s.pageName estiver definido.
* Defina s.prop10 com o tempo de carregamento da página anterior.
* Defina s.prop11 e s.eVar10 com o nome da página anterior (como registrado em s.pageName).
* Defina event100, que seria um evento numérico personalizado, com o tempo de carregamento da página anterior.   Usar um evento personalizado nesse caso permitiria obter a quantidade total de tempo de todos os carregamentos de página da página anterior (de todos os visitantes/visitas) e, portanto, permitiria usar uma métrica calculada para obter o tempo médio de carregamento para cada página.

## Histórico da versão

### 2.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 1.0 (22 de maio de 2018)

* Versão inicial.
