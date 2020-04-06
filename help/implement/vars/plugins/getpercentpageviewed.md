---
title: getPercentPageViewed
description: Recupere a porcentagem da página que o visitante visualizou.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: getPercentPageViewed

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getPercentPageViewed` mede a atividade de rolagem de um visitante para ver quanto de uma página ele visualiza antes de passar para outra página. Esse plug-in não é necessário se as páginas tiverem uma altura pequena ou se você não quiser medir a atividade de rolagem.

## Instale o plug-in usando o editor de código personalizado do Launch

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Amplie o [!UICONTROL Configure tracking using custom code] acordeão, que revela o [!UICONTROL Open Editor] botão.
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v4.0 w/handlePPVevents helper function (Requires p_fo plug-in) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange="undefined"===typeof ch||!0==ch?!0:!1;if("undefined"=== typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()), s.p_fo("s_gppvLoad") &&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:"",s._ppvFoldsSeen=a[4]?a[4]:"",s._ppvFoldsAvailable=a[5]?a[5]:""};

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v4.0 Plugin) */
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,g=s_c_il.length;c<g;c++)if(s_c_il[c]&& (s_c_il[c].getPercentPageViewed||s_c_il[c].getPreviousPageActivity)){var s=s_c_il[c];break}if(s&&s.ppvID){var f=Math.max (Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight, document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),h= window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;c=(window.pageYOffset|| window.document.documentElement.scrollTop||window.document.body.scrollTop)+h;g=Math.min(Math.round(c/f*100),100);var k=Math.floor(c/h);h=Math.floor(f/h);var d="";if(!s.c_r("s_tp")||s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID) ||1==s.ppvChange&&s.c_r("s_tp")&&f!=s.c_r("s_tp")){(s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID+"1"))&&s.c_w("s_ips",c);if(s.c_r("s_tp")&&s.unescape(s.c_r("s_ppv").split(",")[0])===s.ppvID){s.c_r("s_tp");d=s.c_r("s_ppv");var e=-1< d.indexOf(",")?d.split(","):[];d=e[0]?e[0]:"";e=e[3]?e[3]:"";var l=s.c_r("s_ips");d=d+","+Math.round(e/f*100)+","+Math.round(l/ f*100)+","+e+","+k}s.c_w("s_tp",f)}else d=s.c_r("s_ppv");var b=d&&-1<d.indexOf(",")?d.split(",",6):[];f=0<b.length?b[0]: escape(s.ppvID);e=1<b.length?parseInt(b[1]):g;l=2<b.length?parseInt(b[2]):g;var m=3<b.length?parseInt(b[3]):c,n=4<b.length? parseInt(b[4]):k;b=5<b.length?parseInt(b[5]):h;0<g&&(d=f+","+(g>e?g:e)+","+l+","+(c>m?c:m)+","+(k>n?k:n)+","+(h>b?h:b)); s.c_w("s_ppv",d)}}};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
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

### v4.0 (7 de outubro de 2019)

* Adicionadas as soluções `s._ppvFoldsSeen` e `s._ppvFoldsAvailable`

### v3.01 (13 de agosto de 2018)

* Corrigido um problema em páginas com vários objetos AppMeasurement

### v3.0 (13 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código)
* O plug-in agora cria variáveis a serem atribuídas às variáveis do Adobe Analytics em vez de valores de retorno
