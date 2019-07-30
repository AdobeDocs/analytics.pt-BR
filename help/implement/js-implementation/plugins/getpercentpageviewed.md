---
description: Mede a atividade de rolagem de um visitante para ver quanto de uma página ele visualiza antes de passar para outra página. Esse plug-in permite determinar a quantidade de conteúdo que seus usuário exibem em média, para que você possa otimizar o tamanho e os layouts das páginas com base nos comportamentos do usuário.
keywords: Implementação do Analytics
seo-description: Mede a atividade de rolagem de um visitante para ver quanto de uma página ele visualiza antes de passar para outra página. Esse plug-in permite determinar a quantidade de conteúdo que seus usuário exibem em média, para que você possa otimizar o tamanho e os layouts das páginas com base nos comportamentos do usuário.
seo-title: getPercentPageViewed
solution: Analytics
subtopic: Plug-ins
title: getPercentPageViewed
topic: Desenvolvedor e implementação
uuid: 1751 dcdb -699 f -4 bd 1-8 bcb -5 e 62 fa 24896 a
translation-type: tm+mt
source-git-commit: f9912a0da5930be965e4d249f3d2c1891cfd6ed6

---


# getPercentPageViewed

O plug-plugin getpercentpageviewed mede a atividade de rolagem de um visitante para ver a quantidade de páginas que o visitante viu antes de passar para outra página.

>[!NOTE]
>Não é necessário usar o plug-plugin getpercentpageviewed se suas páginas da Web forem pequenas em altura e não houver necessidade de medir a rolagem dos visitantes. Além disso, se você deseja medir a atividade de rolagem somente nas páginas de saída, não é possível usar esse plug-in.

## Pré-requisitos

Você deve ter o appmeasurement e o plug-plugin de ajuda handleppvevents para executar o plug-plugin getpercentpageviewed.

## Implementação

To implement this plugin, copy and paste the code to anywhere within the **[!UICONTROL Plugins]** section of the [!DNL AppMeasurement] file.

>[!NOTE]
>Adicionar os comentários/números de versão com negrito do código ao arquivo appmeasurement ajuda a Adobe Consulting a solucionar problemas de implementação potencial.

You can run the `getPercentPageViewed` function as needed within the doPlugins function (see example calls below.)

## Argumentos para passar

| Argumento | Definição |
|---|---|
| pid (opcional, string) | Um identificador de página correlacionado às porcentagens fornecidas pelas medições de plug-in. Assume como padrão a variável pagename do Analytics ou o URL se a variável pagename não estiver definida |
| ch (opcional, booleano) | " True "é o valor recomendado/padrão para esse argumento. Defina isso como "false" se você não quiser que esse plug-plugin considere quaisquer alterações feitas no tamanho de uma página após sua carga inicial, devido a código de SPA, HTML dinâmico etc. |

## Devoluções

O plug-plugin getpercentpageviewed não retorna nada. Em vez disso, define as seguintes variáveis no objeto AppMeasurement:

* `s._ppvPreviousPage`: O nome da página anterior visualizada (porque as medições finais não estão disponíveis até que uma nova página seja carregada.)
* `s._ppvHighestPercentViewed`: A porcentagem mais alta da página anterior que o visitante visualizou (em altura). Em outras palavras, o ponto mais distante que o visitante rolou para baixo na página anterior.
* `s._ppvInitialPercentViewed`: A porcentagem da página anterior que estava visível quando a página anterior carregada pela primeira vez.
* `s._ppvHighestPixelSeen`: o maior número dos pixels totais vistos (em relação à altura) quando o visitante rolou pela página anterior.

## Cookies

The getPercentPageViewed plugin creates a cookie, called `s_ppv`, that is passed from page to page. O conteúdo do cookie contém os valores inseridos nas quatro variáveis descritas acima e expira no final da sessão.

## Exemplo de chamadas

**Chamada de amostra 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

A amostra de código acima:
* Determina se s. pagename está definido e, se assim for, o código executará a função getpercentpageviewed.
* When the `getPercentPageViewed` function runs, it creates the variables described in the "Returns" section above.
* Se as variáveis "Retorna" foram definidas com sucesso:

   * The code sets s.prop1 equal to the value of `s._ppvPreviousPag`e (i.e. the previous value of `s.pageName`, or the previous page.)
   * O código também define s. prop 2 igual à porcentagem mais alta visualizada da página anterior e à porcentagem inicial visualizada da página anterior.

>[!NOTE]
>Se uma página inteira estiver visível quando carregada pela primeira vez, a porcentagem mais alta exibida e as dimensões Porcentagem inicial visualizadas seriam iguais a 100. Entretanto, se uma página inteira não estiver visível quando carregada pela primeira vez, mas o visitante nunca rolar a página antes de avançar para a próxima página, a porcentagem mais alta exibida e as dimensões Porcentagem inicial visualizada seriam iguais ao mesmo valor.

**Chamada de amostra 2**

Suponha que s. prop 5 tenha sido configurado para capturar um "tipo de página" em vez do nome inteiro da página.

O código a seguir determina se s. prop 5 foi definido e, nesse caso, armazena o valor como a "página anterior" para correlacionar com a porcentagem mais alta exibida e as dimensões Porcentagem inicial visualizada. The value is still stored in the `s._ppvPreviousPage` variable but can be treated as if it were the previous page type instead of the previous page name.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## Substituição do objeto S

Ao instanciar o objeto principal da biblioteca appmeasurement com um nome diferente de "s", altere a seguinte parte do código do plug-plugin:

`s.getPercentPageViewed=function(pid,ch)`

para isso:

`[objectname].getPercentPageViewed=function(pid,ch)`

## Código para implantar

SEÇÃO DE PLUG-INS: adicione o seguinte código à área do arquivo `s_code.js` rotulada como SEÇÃO DE PLUG-INS. Não faça alterações nessa parte do código do plug-in.

```
/******************************************* BEGIN CODE TO DEPLOY *******************************************/ 
/* Adobe Consulting Plugin: getPercentPageViewed v3.01 w/handlePPVevents helper function (Requires AppMeasurement and p_fo plugin) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); 
pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange=ch?ch:!0;if("undefined"===typeof s.linkType||"o"!==
s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()),s.p_fo("s_gppvLoad")&&window
.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1),window.addEventListener("resize",s.handlePPVevents,!1)),s._ppvPreviousPage
=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:""}; 

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v3.01 Plugin) */ 
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,d=s_c_il.length;c<d;c++)if(s_c_il[c]&&s_c_il[c].getPercentPageViewed){var a=s_c_il[c];break}if(a&&a.ppvID){var f=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.
body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round
(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&
a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}}; 

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ 
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```
