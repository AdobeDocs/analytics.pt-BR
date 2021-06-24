---
title: getPercentPageViewed
description: Recupere a porcentagem da página que o visitante visualizou.
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: 633ba0b9a3fe40bfd1b36820949810c631597397
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 98%

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
/* Adobe Consulting Plugin: getPercentPageViewed v5.0.1 */
function getPercentPageViewed(pid,ch){var n=pid,r=ch;function p(){if(window.ppvID){var a=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,d=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,f=Math.min(Math.round(d/a*100),100),l=Math.floor(d/b);b=Math.floor(a/b);var c="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&a!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",d);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");c=window.cookieRead("s_ppv");var h=-1<c.indexOf(",")?c.split(","):[];c=h[0]?h[0]:"";h=h[3]?h[3]:"";var q=window.cookieRead("s_ips");c=c+","+Math.round(h/a*100)+","+Math.round(q/a*100)+","+h+","+l}window.cookieWrite("s_tp",a)}else c=window.cookieRead("s_ppv");var k=c&&-1<c.indexOf(",")?c.split(",",6):[];a=0<k.length?k[0]:encodeURIComponent(window.ppvID);h=1<k.length?parseInt(k[1]):f;q=2<k.length?parseInt(k[2]):f;var t=3<k.length?parseInt(k[3]):d,u=4<k.length?parseInt(k[4]):l;k=5<k.length?parseInt(k[5]):b;0<f&&(c=a+","+(f>h?f:h)+","+q+","+(d>t?d:t)+","+(l>u?l:u)+","+(b>k?b:k));window.cookieWrite("s_ppv",c)}}if("-v"===n)return{plugin:"getPercentPageViewed",version:"5.0.1"};var m=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof m&&(m.contextData.getPercentPageViewed="5.0.1");window.pageName="undefined"!==typeof m&&m.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,d){if("string"===typeof a){var f=window.location.hostname,l=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){l=2<l?l:2;var c=f.lastIndexOf(".");if(0<=c){for(;0<=c&&1<l;)c=f.lastIndexOf(".",c-1),l--;c=0<c?f.substring(c):f}}g=c;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,d=b.indexOf(" "+a+"="),f=0>d?d:b.indexOf(";",d);return(a=0>d?"":decodeURIComponent(b.substring(d+2+a.length,0>f?b.length:f)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var e=window.cookieRead("s_ppv");e=-1<e.indexOf(",")?e.split(","):[];n=n?n:window.pageName?window.pageName:document.location.href;e[0]=decodeURIComponent(e[0]);window.ppvChange="undefined"===typeof r||1==r?!0:!1;"undefined"!==typeof m&&m.linkType&&"o"===m.linkType||(window.ppvID&&window.ppvID===n||(window.ppvID=n,window.cookieWrite("s_ppv",""),p()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",p,!1),window.addEventListener("click",p,!1),window.addEventListener("scroll",p,!1)),this._ppvPreviousPage=e[0]?e[0]:"",this._ppvHighestPercentViewed=e[1]?e[1]:"",this._ppvInitialPercentViewed=e[2]?e[2]:"",this._ppvHighestPixelsSeen=e[3]?e[3]:"",this._ppvFoldsSeen=e[4]?e[4]:"",this._ppvFoldsAvailable=e[5]?e[5]:"")};
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

### 5.0.1 (22 de junho de 2021)

* Correção de um problema em que determinados caracteres especiais resultavam na quebra do plug-in

### 5.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### v4.0 (7 de outubro de 2019)

* Adicionadas as soluções `s._ppvFoldsSeen` e `s._ppvFoldsAvailable`

### v3.01 (13 de agosto de 2018)

* Corrigido um problema em páginas com vários objetos AppMeasurement

### v3.0 (13 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código)
* O plug-in agora cria variáveis a serem atribuídas às variáveis do Adobe Analytics em vez de valores de retorno
