---
title: getPercentPageViewed
description: Recupere a porcentagem da página que o visitante visualizou.
feature: Variables
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 84%

---

# Plug-in da Adobe: getPercentPageViewed

{{plug-in}}

O plug-in `getPercentPageViewed` mede a atividade de rolagem de um visitante para ver quanto de uma página ele visualiza antes de passar para outra página. Esse plug-in não é necessário se as páginas tiverem uma altura pequena ou se você não quiser medir a atividade de rolagem.

## Instale o plug-in usando a extensão SDK da Web ou SDK da Web.

Este plug-in ainda não é compatível com o SDK da Web.

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
   * Tipo de ação: inicializar getPercentPageViewed
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
/* Adobe Consulting Plugin: getPercentPageViewed v5.1 */
function getPercentPageViewed(pid,ch){var e=pid,i=ch;if("-v"===e)return{plugin:"getPercentPageViewed",version:"5.1"};var t=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();function o(){if(window.ppvID){var e=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),i=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,t=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+i,o=Math.min(Math.round(t/e*100),100),n=Math.floor(e/i),p=Math.floor(t/i),s="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||!0==window.ppvChange&&window.cookieRead("s_tp")&&e!=window.cookieRead("s_tp")){if((decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",t),window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");var a=window.cookieRead("s_ppv"),c=a.indexOf(",")>-1?a.split(","):[],d=c[0]?c[0]:"",r=window.cookieRead("s_ips"),l=c[3]?c[3]:"";s=d+","+Math.round(r/e*100)+","+Math.round(l/e*100)+","+o+","+l+","+n+","+p}window.cookieWrite("s_tp",e)}else s=window.cookieRead("s_ppv");var v=s&&s.indexOf(",")>-1?s.split(",",7):[],f=v.length>0?v[0]:encodeURIComponent(window.ppvID),$=v.length>1?parseInt(v[1]):o,h=v.length>2?parseInt(v[2]):o,u=v.length>4?parseInt(v[4]):t,k=v.length>5?parseInt(v[5]):n,m=v.length>6?parseInt(v[6]):p;o>0&&(s=f+","+$+","+(o>h?o:h)+","+o+","+(t>u?t:u)+","+(n>k?n:k)+","+(p>m?p:m)),window.cookieWrite("s_ppv",s)}}void 0!==t&&(t.contextData.getPercentPageViewed="5.1"),window.pageName=void 0!==t&&t.pageName||"",window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){if(g=function(){var e=window.location.hostname,i=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){i=2<i?i:2;var t=e.lastIndexOf(".");if(0<=t){for(;0<=t&&1<i;)t=e.lastIndexOf(".",t-1),i--;t=0<t?e.substring(t):e}}return t}(),i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var o=new Date;o.setTime(o.getTime()+6e4*t)}else o=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),void 0!==window.cookieRead)&&window.cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),o=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>o?i.length:o)))?e:""},window.p_fo=window.p_fo||function(e){return window.__fo||(window.__fo={}),!window.__fo[e]&&(window.__fo[e]={},!0)};var n=window.cookieRead("s_ppv"),p=n.indexOf(",")>-1?n.split(","):[];p[0]=p.length>0?decodeURIComponent(p[0]):"",e=e||(window.pageName?window.pageName:document.location.href),void 0===i||!0==i?window.ppvChange=!0:window.ppvChange=!1,void 0!==t&&t.linkType&&"o"===t.linkType||(window.ppvID&&window.ppvID===e||(window.ppvID=e,window.cookieWrite("s_ppv",""),o()),window.p_fo("s_gppvLoad2")&&window.addEventListener&&(window.addEventListener("load",o,!1),window.addEventListener("click",o,!1),window.addEventListener("scroll",o,!1)),this._ppvPreviousPage=p[0]?p[0]:"",this._ppvInitialPercentViewed=p[1]?p[1]:"",this._ppvHighestPercentViewed=p[2]?p[2]:"",this._ppvFinalPercentViewed=p[3]?p[3]:"",this._ppvHighestPixelsSeen=p[4]?p[4]:"",this._ppvFoldsAvailable=p[5]?p[5]:"",this._ppvFoldsSeen=p[6]?p[6]:"")}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getPercentPageViewed` usa os seguintes argumentos:

* **`pid`** (opcional, string): uma variável ou valor igual à página atual. Assume o padrão da variável AppMeasurement `pageName` do Analytics OU o URL se a variável AppMeasurement pageName não estiver definida.
* **`ch`** (opcional, booleano): defina como `false` (ou `0`) se você não quiser que o plug-in não ignore quaisquer alterações feitas no tamanho de uma página após o carregamento inicial. Se omitido, esse argumento assumirá `true` como padrão. A Adobe recomenda omitir esse argumento na maioria dos casos.

Chamar essa função não retorna nada; em vez disso, ele define as seguintes variáveis:

* `window._ppvPreviousPage`: o nome da página exibida anteriormente. As medições finais de rolagem da página atual não estarão disponíveis até que uma nova página seja carregada.
* `window._ppvInitialPercentViewed`: a porcentagem da página anterior que estava visível quando a página anterior foi carregada pela primeira vez. Se a página inteira estiver visível quando carregada pela primeira vez, esse valor será `100`.
* `window._ppvHighestPercentViewed`: a porcentagem mais alta da página anterior que o visitante visualizou (em termos de altura). O ponto mais distante que o visitante chegou quando rolou para baixo na página anterior. Se a página inteira estiver visível quando carregada pela primeira vez, esse valor será `100`.
* `window._ppvFinalPercentViewed`: a porcentagem da página anterior que estava visível no ponto em que o visitante foi para a página atual. Esse valor será igual ou maior que a porcentagem inicial visualizada e também será igual ou inferior à porcentagem mais alta visualizada da página.
* `window._ppvHighestPixelsSeen`: o maior número dos pixels totais vistos (em relação à altura) quando o visitante rolou pela página anterior.
* `window._ppvFoldsAvailable`: o número total de &quot;dobras de página&quot; disponíveis na rolagem para baixo da página anterior. Se a página inteira estiver visível quando carregada pela primeira vez, esse valor será `1`.
* `window._ppvFoldsSeen`: o maior número de &quot;dobras de página&quot; totais vistas (em relação à altura) quando o visitante rolou pela página anterior. Essa variável inclui a dobra do &quot;início da página&quot;. Se a página inteira estiver visível quando carregada pela primeira vez, esse valor será `1`.

Atribua uma ou mais dessas variáveis a eVars para ver dados de dimensão em relatórios.

Este plug-in cria três cookies primários que expiram no final de uma sessão do navegador:

* `s_ppv`: armazena cada um dos valores expostos ao chamar a função
* `s_tp`: armazena a altura total dos pixels da página anterior
* `s_ips`: armazena a porcentagem inicial rolada da página anterior

## Exemplos

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the intial percent, the highest percent, and the final percent viewed; the number of folds available on the page, and the number of folds viewed ( of the previous page)
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed + " | finalPercent=" + _ppvFinalPercentViewed + " | foldsAvailable=" + _ppvFoldsAvailable + " | foldsSeen=" + _ppvFoldsSeen;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page type
// 3. Sets prop2 to the initial percent viewed and the highest percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed;
}
```

## Histórico da versão

### 5.1 (8 de dezembro de 2022)

* A solução `_finalPercentViewed` foi adicionada

### 5.0.1 (22 de junho de 2021)

* Correção de um problema em que determinados caracteres especiais resultavam em falha do plug-in

### 5.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### v4.0 (7 de outubro de 2019)

* Adicionadas as soluções `s._ppvFoldsSeen` e `s._ppvFoldsAvailable`

### v3.01 (13 de agosto de 2018)

* Corrigido um problema em páginas com vários objetos AppMeasurement

### v3.0 (13 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código)
* O plug-in agora cria variáveis a serem atribuídas às variáveis do Adobe Analytics em vez de valores de retorno
