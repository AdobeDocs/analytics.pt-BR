---
description: Mede a atividade de rolagem de um visitante para ver quanto de uma página ele visualiza antes de passar para outra página. Esse plug-in permite determinar a quantidade de conteúdo que seus usuário exibem em média, para que você possa otimizar o tamanho e os layouts das páginas com base nos comportamentos do usuário.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getPercentPageViewed
topic: Developer and implementation
uuid: 1751dcdb-699f-4bd1-8bcb-5e62fa24896a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getPercentPageViewed

O plug-in getPercentPageViewed mede a atividade de rolagem de um visitante para ver quanto de uma página o visitante visualizou antes de ir para outra página.

>[!NOTE]
>Você não precisar usar o plug-in getPercentPageViewed se a altura das páginas da Web for baixa e não houver necessidade de medir a distância de rolagem dos visitantes. Além disso, se você deseja medir a atividade de rolagem somente nas páginas de saída, não é possível usar esse plug-in.

## Pré-requisitos

Você deve ter o AppMeasurement e o plug-in handPPVevents helper para executar o plug-in getPercentPageViewed.

## Implementação

Para implementar esse plug-in, copie e cole o código em qualquer lugar na seção **[!UICONTROL Plug-ins]** do arquivo [!DNL AppMeasurement].

>[!NOTE]
>Adicionar os comentários em negrito/números de versão do código ao arquivo AppMeasurement ajuda a Adobe Consulting a solucionar possíveis problemas de implementação.

Você pode executar a função `getPercentPageViewed` conforme necessário na função doPlugins (consulte exemplos de chamadas abaixo).

## Argumentos para ser transmitidos

| Argumento | Definição |
|---|---|
| pid (opcional, string) | Um identificador de página que está correlacionado com as porcentagens fornecidas pelas medições do plug-in. Assume o padrão da variável pageName do Analytics ou o URL se a variável pageName não estiver definida |
| ch (opcional, booleano) | "True" é o valor recomendado/padrão para esse argumento. Defina esse valor como "false" se você não quiser que esse plug-in considere as alterações feitas no tamanho da página, após o carregamento inicial, devido ao código SPA, HTML dinâmico, etc.. |

## Devoluções

O plug-in getPercentPageViewed não retorna nada. Em vez disso, define as seguintes variáveis no objeto AppMeasurement:

* `s._ppvPreviousPage`: o nome da página anterior visualizada (porque as medidas finais não estão disponíveis até que uma nova página seja carregada).
* `s._ppvHighestPercentViewed`: a porcentagem mais alta da página anterior que o visitante visualizou (em termos de altura). Em outras palavras, o ponto mais distante que o visitante percorreu na página anterior.
* `s._ppvInitialPercentViewed`: a porcentagem da página anterior que estava visível quando a página anterior foi carregada pela primeira vez.
* `s._ppvHighestPixelSeen`: o maior número dos pixels totais vistos (em relação à altura) quando o visitante rolou pela página anterior.

## Cookies

O plug-in getPercentPageViewed cria um cookie, chamado `s_ppv`, que é transmitido de uma página para outra. O conteúdo do cookie contém os valores inseridos nas quatro variáveis descritas acima e expiram no final da sessão.

## Exemplos de chamadas

**Exemplo de chamada 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

A amostra de código acima:
* Determina se s.pageName foi definido e, nesse caso, o código executará a função getPercentPageViewed.
* Quando a função `getPercentPageViewed` é executada, ela cria as variáveis descritas na seção "Retornos" acima.
* Se as variáveis "Retornos" foram definidas com êxito:

   * O código define s.prop1 igual ao valor de `s._ppvPreviousPag`e (ou seja, o valor anterior de `s.pageName` ou a página anterior).
   * O código também define s.prop2 igual à Porcentagem mais alta visualizada da página anterior e a Porcentagem inicial visualizada da página anterior.

>[!NOTE]
>Se uma página inteira estiver visível quando for carregada pela primeira vez, as dimensões Porcentagem mais alta visualizada e Porcentagem inicial visualizada serão iguais a 100. Entretanto, se uma página inteira não estiver visível quando for carregada pela primeira vez, mas o visitante não rolar pela página antes de ir para a próxima, as dimensões Porcentagem mais alta visualizada e Porcentagem inicial visualizada serão iguais ao mesmo valor.

**Exemplo de chamada 2**

Suponha que s.prop5 tenha sido reservado para capturar um "tipo de página" acumulado, em vez do nome da página inteira.

O código a seguir determina se s.prop5 foi definido e, nesse caso, armazena seu valor como a "página anterior" para correlacionar-se com a Porcentagem mais alta visualizada e a Porcentagem inicial visualizada. O valor ainda é armazenado na variável `s._ppvPreviousPage`, mas pode ser tratado como se fosse o tipo de página anterior, em vez do nome da página anterior.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## Substituição do objeto S

Ao instanciar o objeto principal da biblioteca do AppMeasurement com um nome diferente de "s", altere a seguinte parte do código do plug-in desta opção:

`s.getPercentPageViewed=function(pid,ch)`

para isto:

`[objectname].getPercentPageViewed=function(pid,ch)`

## Código para implantação

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
