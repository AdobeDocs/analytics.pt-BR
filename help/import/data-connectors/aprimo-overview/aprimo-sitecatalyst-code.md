---
description: Se você selecionou o método de coleta de dados do Plug-in javascript, copie as seguintes linhas de código e adicione-as ao código do Adobe Analytics nas suas páginas.
seo-description: Se você selecionou o método de coleta de dados do Plug-in javascript, copie as seguintes linhas de código e adicione-as ao código do Adobe Analytics nas suas páginas.
seo-title: Código de plug-in do Adobe Analytics
title: Código de plug-in do Adobe Analytics
uuid: 60 d 80366-d 144-465 a-b 3 de-acc 2341 be 1 cd
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Código de plug-in do Adobe Analytics {#adobe-analytics-plug-in-code}

Se você selecionou o método de coleta de dados do Plug-in javascript, copie as seguintes linhas de código e adicione-as ao código do Adobe Analytics nas suas páginas.

`/*`

`* Plugin: getQueryParam 2.3`

`*/ s.getQueryParam=new Function("p","d","u","" +"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" +"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" +".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" +"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" +"=p.length?i:i+1)}return v"); s.p_gpv=new Function("k","u","" +"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" +"=s.pt(q,'&','p_gvf',k)}return v"); s.p_gvf=new Function("t","k","" +"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" +"rue':t.substring(i+1);if(p.toLowerCase()==k. oLowerCase())return s." +"epa(v)}return ''");`

`/*in the s_doPlugins function`

`s.campaign=s.getQueryParam("ET_CID"); //places query param value from cid in campaign variable s.eVar2=s.getQueryParam("ET_RID"); //places query param value from rid in eVar2 variable`

>[!NOTE]
>
>O plug-plugin acima presume que determinadas Variáveis de comércio personalizadas (evars) estejam disponíveis. Se as variáveis especificadas no plug-plugin acima não estiverem disponíveis na implantação do Adobe Analytics, substitua-as por aquelas disponíveis.

