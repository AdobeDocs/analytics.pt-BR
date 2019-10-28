---
description: O Analytics oferece diversas variáveis para coletar dados do Analytics. Por exemplo, o valor na variável pageName é o nome da página da Web que está sendo reportada. Esta seção lista as variáveis compatíveis com o AppMeasurement.
keywords: Implementação do Analytics, variáveis appmeasurement
seo-description: O Analytics oferece diversas variáveis para coletar dados do Analytics. Por exemplo, o valor na variável pageName é o nome da página da Web que está sendo reportada. Esta seção lista as variáveis compatíveis com o AppMeasurement.
seo-title: Visão geral das variáveis
solution: Analytics
subtopic: Variáveis
title: Visão geral das variáveis
topic: Desenvolvedor e implementação
uuid: 067d0135-572a-4a44-af9e-445d3c4e9271
translation-type: ht
source-git-commit: 40e9872126114588961a1e84e6be85bb945050a4

---


# Visão geral das variáveis

O Analytics oferece diversas variáveis para coletar dados do Analytics. Por exemplo, o valor na variável pageName é o nome da página da Web que está sendo reportada. Esta seção lista as variáveis compatíveis com o AppMeasurement.

Para obter mais informações sobre as Variáveis de página, clique [aqui](/help/implement/js-implementation/c-variables/page-variables.md).
Para obter mais informações sobre as Variáveis de configuração, clique [aqui](/help/implement/js-implementation/c-variables/configuration-variables.md).

## Como definir variáveis {#section_E52CF9E8FDF74164A1511E0D9D31884D}

AppMeasurement requer que todas as variáveis de configuração sejam definidas antes da chamada inicial à função de rastreamento, *`t()`*. Se as variáveis de configuração forem definidas após a chamada para *`t()`*, podem ocorrer resultados inesperados.

As variáveis de configuração são definidas na função *`doPlugins`*, que é chamada durante a execução da função de rastreamento. A variável de configuração específica que está causando esse problema é *`trackInlineStats`*, que permite a coleta de dados do ClickMap. Isso deixa o módulo ClickMap em um estado indeterminado, que resulta na primeira chamada de rastreamento e anexa a cadeia de caracteres "undefined" ao beacon do Adobe Analytics, e afeta o código de moeda.

Para resolver este problema, mova todas as variáveis de configuração para acima da função doPlugins.

```
/************************** CONFIG SECTION **************************/ 
/* Ensure these variables are correct before deploying */ 
var s_account="[INSERT-REPORT-SUITE-ID-HERE]" 
var s=s_gi(s_account) 
s.trackingServer="[INSERT-TRACKING-SERVER-HERE]" 
s.visitorNamespace="[INSERT-VISITOR-NAMESPACE-HERE]" 
s.charSet="ISO-8859-1" 
s.currencyCode="USD" 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" 
s.linkInternalFilters="javascript:,three,two,one,dev16,.,nike" 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.debugTracking=true 
 
s.usePlugins=true; 
function s_doPlugins(s) { 
    //add your custom plugin code here 
} 
s.doPlugins=s_doPlugins; 
 
/* 
============== DO NOT ALTER ANYTHING BELOW THIS LINE ! =============== 
 
AppMeasurement for JavaScript version: 1.5.3 
Copyright 1996-2016 Adobe, Inc. All Rights Reserved 
More info available at https://www.omniture.com 
*/ 
function AppMeasurement(){var a=this;a.version="1.5.3";var k=window;k.s_c_in||(k.s_c_il=[],k.s_c_in=0);a._il=k.s_c_il;a._in=k.s_c_in;a._il[a._in]=a;k.s_c_in++;a._c="s_c";var q=k.AppMeasurement.zb;q||(q=null);var r=k,n,t;try{for(n=r.parent,t=r.location;n&&n.location&&t&&""+n.location!=""+t&&r.location&&""+n.location!=""+r.location&&n.location.host==t.host;)r=n,n=r.parent}catch(u){}a.ob=function(a){try{console.log(a)}catch(b){}};a.za=function(a){return""+parseInt(a)==""+a};a.replace=function(a,b,d){return!a|| 
0>a.indexOf(b)?a:a.split(b).join(d)};a.escape=function(c){var b,d;if(!c)return c;c=encodeURIComponent(c);for(b=0;7>b;b++)d="+~!*()'".substring(b,b+1),0<=c.indexOf(d)&&(c=a.replace(c,d,"%"+d.charCodeAt(0).toString(16).toUpperCase()));return c};a.unescape=function(c){if(!c)return c;c=0<=c.indexOf("+")?a.replace(c,"+"," "):c;try{return decodeURIComponent(c)}catch(b){}return unescape(c)};a.gb=function(){var c=k.location.hostname,b=a.fpCookieDomainPeriods,d;b||(b=a.cookieDomainPeriods);if(c&&!a.cookieDomain&& 
```

