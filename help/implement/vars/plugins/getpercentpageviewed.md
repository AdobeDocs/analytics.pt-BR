---
title: getPercentPageViewed
description: Recupere a porcentagem da página que o visitante visualizou.
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: c08be9abf73f4ef2007710839966257350b98f12
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 100%

---

# Plug-in da Adobe: getPercentPageViewed

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getPercentPageViewed` mede a atividade de rolagem de um visitante para ver quanto de uma página ele visualiza antes de passar para outra página. Esse plug-in não é necessário se as páginas tiverem uma altura pequena ou se você não quiser medir a atividade de rolagem.

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
   * Tipo de ação: inicializar getPercentPageViewed
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do Launch

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
/* Adobe Consulting Plugin: getPercentPageViewed v5.0 w/handlePPVevents helper function (Requires AppMeasurement and the p_fo plugin) */
function getPercentPageViewed(pid,ch){var l=pid,p=ch;function m(){if(window.ppvID){var c=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,k=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,a=Math.min(Math.round(k/c*100),100),n=Math.floor(k/b);b=Math.floor(c/b);var d="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&c!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",k);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");d=window.cookieRead("s_ppv");var f=-1<d.indexOf(",")?d.split(","):[];d=f[0]?f[0]:"";f=f[3]?f[3]:"";var e=window.cookieRead("s_ips");d=d+","+Math.round(f/c*100)+","+Math.round(e/c*100)+","+f+","+n}window.cookieWrite("s_tp",c)}else d=window.cookieRead("s_ppv");var h=d&&-1<d.indexOf(",")?d.split(",",6):[];c=0<h.length?h[0]:escape(window.ppvID);f=1<h.length?parseInt(h[1]):a;e=2<h.length?parseInt(h[2]):a;var l=3<h.length?parseInt(h[3]):k,m=4<h.length?parseInt(h[4]):n;h=5<h.length?parseInt(h[5]):b;0<a&&(d=c+","+(a>f?a:f)+","+e+","+(k>l?k:l)+","+(n>m?n:m)+","+(b>h?b:h));window.cookieWrite("s_ppv",d)}}if("-v"===l)return{plugin:"getPercentPageViewed",version:"5.0"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPercentPageViewed="5.0");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(c,b,a){if("string"===typeof c){var k=window.location.hostname,e=window.location.hostname.split(".").length-1;if(k&&!/^[0-9.]+$/.test(k)){e=2<e?e:2;var d=k.lastIndexOf(".");if(0<=d){for(;0<=d&&1<e;)d=k.lastIndexOf(".",d-1),e--;d=0<d?k.substring(d):k}}g=d;b="undefined"!==typeof b?""+b:"";if(a||""===b)if(""===b&&(a=-60),"number"===typeof a){var f=new Date;f.setTime(f.getTime()+6E4*a)}else f=a;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(a?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),e=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>e?b.length:e)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var a=window.cookieRead("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];l=l?l:window.pageName?window.pageName:document.location.href;a[0]=decodeURIComponent(a[0]);window.ppvChange="undefined"===typeof p||1==p?!0:!1;"undefined"!==typeof e&&e.linkType&&"o"===e.linkType||(window.ppvID&&window.ppvID===l||(window.ppvID=l,window.cookieWrite("s_ppv",""),m()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",m,!1),window.addEventListener("click",m,!1),window.addEventListener("scroll",m,!1)),window._ppvPreviousPage=a[0]?a[0]:"",window._ppvHighestPercentViewed=a[1]?a[1]:"",window._ppvInitialPercentViewed=a[2]?a[2]:"",window._ppvHighestPixelsSeen=a[3]?a[3]:"",window._ppvFoldsSeen=a[4]?a[4]:"",window._ppvFoldsAvailable=a[5]?a[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getPercentPageViewed` aceita os seguintes argumentos:

* **`pid`** (opcional, string): um identificador em páginas que você pode correlacionar com as porcentagens fornecidas pelas medições do plug-in.  O padrão é a variável `pageName`.
* **`ch`** (opcional, booleano): defina como `false` (ou `0`) se você não quiser que o plug-in não ignore quaisquer alterações feitas no tamanho de uma página após o carregamento inicial. Se omitido, esse argumento assumirá `true` como padrão. A Adobe recomenda omitir esse argumento na maioria dos casos.

Chamar esse método não retorna nada; em vez disso, ele define as seguintes variáveis:

* `s._ppvPreviousPage`: o nome da página exibida anteriormente. As medições finais de rolagem da página atual não estarão disponíveis até que uma nova página seja carregada.
* `s._ppvHighestPercentViewed`: a porcentagem mais alta da página anterior que o visitante visualizou (em termos de altura). O ponto mais distante que o visitante chegou quando rolou para baixo na página anterior.
* `s._ppvInitialPercentViewed`: a porcentagem da página anterior que estava visível quando a página anterior foi carregada pela primeira vez.
* `s._ppvHighestPixelsSeen`: o maior número dos pixels totais vistos (em relação à altura) quando o visitante rolou pela página anterior.
* `s._ppvFoldsSeen`: o maior número de &quot;dobras de página&quot; totais vistas (em relação à altura) quando o visitante rolou pela página anterior. Essa variável inclui a dobra do &quot;início da página&quot;.
* `s._ppvFoldsAvailable`: o número total de &quot;dobras de página&quot; disponíveis na rolagem para baixo da página anterior.

Atribua uma ou mais dessas variáveis a eVars para ver dados de dimensão em relatórios.

Este plug-in cria um cookie próprio chamado `s_ppv` que contém os valores acima. Ele expira no final da sessão do navegador.

## Exemplos de chamadas

### Exemplo #1

O código a seguir...

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* Determina se s.pageName foi definido e, nesse caso, o código executará a função getPercentPageViewed
* Quando a função getPercentPageViewed é executada, ela cria as variáveis descritas na seção &quot;Retornos&quot; acima
* Se as variáveis em &quot;Retornos&quot; foram definidas com êxito:
   * O código define s.prop1 com o valor de s._ppvPreviousPage (ou seja, o valor anterior de s.pageName ou da página anterior)
   * O código também definirá s.prop2 como a mais alta porcentagem visualizada e a porcentagem inicial visualizada da página anterior, juntamente com o número de dobras que o visitante visualizou e o número de dobras que estavam disponíveis

**Observação**: se uma página inteira estiver visível quando carregada pela primeira vez, tanto a porcentagem mais alta visualizada quanto as dimensões da porcentagem inicial visualizada serão iguais a 100, e ambas as dimensões Dobras Visualizadas e Dobras Disponíveis serão iguais a 1.   Entretanto, se uma página inteira não estiver visível quando carregada pela primeira vez, mas o visitante acabar não rolando a página antes de ir para a próxima, então as dimensões Porcentagem mais alta visualizada e Porcentagem inicial visualizada terão o mesmo valor.

### Exemplo #2

Suponha que s.prop5 tenha sido reservado para capturar um &quot;tipo de página&quot; acumulado, em vez do nome da página inteira.

O código a seguir determina se s.prop5 foi definido e, nesse caso, armazenará seu valor como a &quot;página anterior&quot; para correlacionar-se com as dimensões Porcentagem mais alta visualizada e Porcentagem inicial visualizada.  O valor ainda será armazenado na variável s._ppvPreviousPage, mas pode ser tratado como se fosse o tipo de página anterior, em vez do nome da página anterior.

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## Histórico da versão

### 5.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### v4.0 (7 de outubro de 2019)

* Adicionadas as soluções `s._ppvFoldsSeen` e `s._ppvFoldsAvailable`

### v3.01 (13 de agosto de 2018)

* Corrigido um problema em páginas com vários objetos AppMeasurement

### v3.0 (13 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código)
* O plug-in agora cria variáveis a serem atribuídas às variáveis do Adobe Analytics em vez de valores de retorno
