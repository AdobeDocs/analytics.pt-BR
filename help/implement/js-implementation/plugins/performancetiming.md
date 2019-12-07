---
description: 'Este plug-in usa a Navigation Timing JavaScript API para medir com precisão o desempenho na Web. Isso fornece um método para obter dados de estatística precisos e detalhados para eventos de carregamento de paginas e tempos de carregamento de ativos. Anteriormente, medidas desse tipo utilizavam o objeto JavaScript Date para métricas de tempo ou uma extrapolação rudimentar das métricas Navigation Timing. Apesar de fornecerem dados de tendência sobre os tempos de carregamento de páginas, ambas as metodologias são incertas. '
keywords: Analytics Implementation
title: performanceTiming
topic: Developer and implementation
uuid: ab2a6c51-8791-41e7-9bea-c1ce8d312de8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# performanceTiming

Este plug-in usa a Navigation Timing JavaScript API para medir com precisão o desempenho na Web. Isso fornece um método para obter dados de estatística precisos e detalhados para eventos de carregamento de paginas e tempos de carregamento de ativos. Anteriormente, medidas desse tipo utilizavam o objeto JavaScript Date para métricas de tempo ou uma extrapolação rudimentar das métricas Navigation Timing. Apesar de fornecerem dados de tendência sobre os tempos de carregamento de páginas, ambas as metodologias são incertas. 

## O que este plug-in faz {#section_4E0771B959FD4F86B4B91BD18CA01DF1}

>[!IMPORTANT]
>
>Observação: está é uma versão beta do plug-in e pode haver mais atualizações no futuro.

Este plug-in usa os seguintes eventos detalhados para rastrear os componentes de tempo individuais de um carregamento de página:

| Evento | Nome | Calculado de |
|---|---|---|
| 1 | Tempo de redirecionamento | fetchStart - navigationStart |
| 2 | Tempo de cache de aplicativos | domainLookupStart - fetchStart |
| 3 | Tempo de DNS | domainLookupEnd - domainLookupStart |
| 4 | Tempo de TCP | connectEnd - connectStart |
| 5 | Tempo de solicitação | responseStart - connectEnd |
| 6 | Tempo de resposta | responseEnd - responseStart |
| 7 | Tempo de processamento | loadEventStart - domLoading |
| 8 | Tempo de onLoad | loadEventEnd - loadEventStart |
| 9 | Tempo total do carregamento da página | loadEventEnd - navigationStart |
| 10 | Instâncias de desempenho | Contador |

O gráfico a seguir ilustra os atributos de tempo definidos pelas interfaces PerformanceTiming e PerformanceNavigation com ou sem redirecionamento, respectivamente.

![](assets/timing-attributes.png)

Obtenha detalhes completos a respeito do objeto Navigation Timing aqui:

[https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface](https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface)

Além disso, o plug-in pode usar, opcionalmente, o objeto performanceEntries para gravar o nome do ativo, tempo de início de carregamento do ativo e detalhes da duração do tempo de carregamento do ativo para cada ativo individual carregado em uma certa página. Uma grande quantidade de informações é gravada com esse plug-in, que requer que o objeto de armazenamento de DOM esteja ativado para que as informações de carregamento de página sejam armazenados por entre as visualizações da página. Certifique-se de que a política de privacidade da sua empresa permita o uso do objeto de armazenamento DOM antes de habilitar essa funcionalidade. Além disso, o uso de uma listVar é exigido para rastrear todos os ativos.

## Plug-ins de suporte exigidos {#section_B6447EB6548942EFBC219AEFDC245639}

* appendList
* getPreviousValue

## Códigos de plug-ins e implementação {#section_564D77E1CF0E445586D95AD9769CE57D}

> [!NOTE] Observação: as instruções a seguir exigem que você altere o código da coleta de dados do seu site. Isso pode afetar a coleta de dados do seu site, e deve ser feito somente por um desenvolvedor com experiência de uso e implementação do Adobe Analytics. Este plug-in é compatível somente com as bibliotecas de rastreamento do [!DNL AppMeasurement].

**Sessão Config (antes de doPlugins):**

`s.pte`: lista de eventos separada por vírgulas contendo os 10 eventos que você deseja usar - os componentes de evento tempo individuais (eventos 1 a 8), o tempo total de carregamento da página (evento 9) e o total de instâncias de desempenho (evento 10) - respectivamente.

`s.ptc`: defina para determinar se o plug-in será executado com doPlugins. Sempre definido como false.

*Solicitações de exemplo*

```
s.pte = 'event10,event11,event12,event13,event14,event15,event16,event17,event18,event19' 
//[--------------------------- 1 to 8 ---------------------------][-- 9 --][- 10 -] 
s.ptc = false; 
```

**Seção doPlugins:**

Para iniciar o plug-in, é preciso ter uma linha de código na sessão `doPlugins` do seu s_code, de preferência depois de designar a variável `s.pageName`. Se você desejar usar o recurso de tempo de carregamento do ativo dentro do plug-in, será preciso passar o nome da variável de lista a ser usada. Caso contrário, somente as entradas de tempo do desempenho serão rastreadas nos eventos especificados anteriormente na variável `s.pte`.

> [!NOTE]Para correlacionar as entradas de tempo de desempenho com as páginas do site, você deve inicializar o plug-in `getPreviousValue`. Recomendamos que você compare as entradas de desempenho com o nome da página anterior ou o valor anterior do URL da página.

*Solicitações de exemplo*

```
/* Performance Timing */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.performanceTiming('list2')  
```

**Seção de plug-ins:**

Por fim, adicione o plug-in à sua implementação do JavaScript.

```
/* Plugin: Performance Timing Tracking - 0.11 BETA */ 
s.performanceTiming=new Function("v","" 
+"var s=this;if(v)s.ptv=v;if(typeof performance!='undefined'){if(perf" 
+"ormance.timing.loadEventEnd==0){s.pi=setInterval(function(){s.perfo" 
+"rmanceWrite()},250);}if(!s.ptc||s.linkType=='e'){s.performanceRead(" 
+");}else{s.rfe();s[s.ptv]='';}}"); 
s.performanceWrite=new Function("","" 
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)" 
+";try{if(s.c_r('s_ptc')==''&&performance.timing.loadEventEnd>0){try{" 
+"var pt=performance.timing;var pta='';pta=s.performanceCheck(pt.fetc" 
+"hStart,pt.navigationStart);pta+='^^'+s.performanceCheck(pt.domainLo" 
+"okupStart,pt.fetchStart);pta+='^^'+s.performanceCheck(pt.domainLook" 
+"upEnd,pt.domainLookupStart);pta+='^^'+s.performanceCheck(pt.connect" 
+"End,pt.connectStart);pta+='^^'+s.performanceCheck(pt.responseStart," 
+"pt.connectEnd);pta+='^^'+s.performanceCheck(pt.responseEnd,pt.respo" 
+"nseStart);pta+='^^'+s.performanceCheck(pt.loadEventStart,pt.domLoad" 
+"ing);pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.loadEventStart" 
+");pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.navigationStart);" 
+"s.c_w('s_ptc',pta);if(sessionStorage&&navigator.cookieEnabled&&s.pt" 
+"v!='undefined'){var pe=performance.getEntries();var tempPe='';for(v" 
+"ar i=0;i<pe.length;i++){tempPe+='!';tempPe+=pe[i].name.indexOf('?')" 
+">-1?pe[i].name.split('?')[0]:pe[i].name;tempPe+='|'+(Math.round(pe[" 
+"i].startTime)/1000).toFixed(1)+'|'+(Math.round(pe[i].duration)/1000" 
+").toFixed(1)+'|'+pe[i].initiatorType;}sessionStorage.setItem('s_pec" 
+"',tempPe);}}catch(err){return;}}}catch(err){return;}"); 
s.performanceCheck=new Function("a","b","" 
+"if(a>=0&&b>=0){if((a-b)<60000&&((a-b)>=0)){return((a-b)/1000).toFix" 
+"ed(2);}else{return 600;}}"); 
s.performanceRead=new Function("","" 
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)" 
+";var cv=s.c_r('s_ptc');if(s.pte){var ela=s.pte.split(',');}if(cv!='" 
+"'){var cva=s.split(cv,'^^');if(cva[1]!=''){for(var x=0;x<(ela.lengt" 
+"h-1);x++){s.events=s.apl(s.events,ela[x]+'='+cva[x],',',2);}}s.even" 
+"ts=s.apl(s.events,ela[ela.length-1],',',2);}s.linkTrackEvents=s.apl" 
+"(s.linkTrackEvents,s.pte,',',2);s.c_w('s_ptc','',0);if(sessionStora" 
+"ge&&navigator.cookieEnabled&&s.ptv!='undefined'){s[s.ptv]=sessionSt" 
+"orage.getItem('s_pec');sessionStorage.setItem('s_pec','',0);}else{s" 
+"[s.ptv]='sessionStorage Unavailable';}s.ptc=true;"); 
/* Remove from Events 0.1 - Performance Specific,  
removes all performance events from s.events once being tracked. */ 
s.rfe=new Function("","" 
+"var s=this;var ea=s.split(s.events,',');var pta=s.split(s.pte,',');" 
+"try{for(x in pta){s.events=s.rfl(s.events,pta[x]);s.contextData['ev" 
+"ents']=s.events;}}catch(e){return;}"); 
/* Plugin Utility - RFL (remove from list) 1.0*/ 
s.rfl=new Function("l","v","d1","d2","ku","" 
+"var s=this,R=new Array(),C='',d1=!d1?',':d1,d2=!d2?',':d2,ku=!ku?0:" 
+"1;if(!l)return'';L=l.split(d1);for(i=0;i<L.length;i++){if(L[i].inde" 
+"xOf(':')>-1){C=L[i].split(':');C[1]=C[0]+':'+C[1];L[i]=C[0];}if(L[i" 
+"].indexOf('=')>-1){C=L[i].split('=');C[1]=C[0]+'='+C[1];L[i]=C[0];}" 
+"if(L[i]!=v&&C)R.push(C[1]);else if(L[i]!=v)R.push(L[i]);else if(L[i" 
+"]==v&&ku){ku=0;if(C)R.push(C[1]);else R.push(L[i]);}C='';}return s." 
+"join(R,{delim:d2})"); 
```

## Notas {#section_131C5D97A0094880AFC3A2BBE0BC9DE4}

* Sempre teste as instalações de plug-ins para garantir que a coleta de dados ocorra como esperado antes de ser implantada em um ambiente de produção.
* Os dados não são coletados para a visualização final de página da visita porque o plug-in passa os dados de desempenho conforme são associados à página anterior.
* Se você estiver rastreando o tempo do ativo, o plug-in dependerá na capacidade de definir valores de armazenamento de DOM no navegador da Web do usuário. Se o usuário não aceita cookies e tiver o armazenamento de DOM ativado, o plug-in não passará os dados ao Analytics. 
* Uma pequena porcentagem de usuários não passa dados de tempo de navegação devido a limitações do navegador. A lógica é mantida dentro do plug-in para garantir que, como resultado, os dados não sejam distorcidos. Em especial, isso ocorre com uma porção pequena de navegadores móveis. No entanto, esse plug-in foi testado com êxito no IE, Firefox, Chrome e Safari.
* [!UICONTROL Métricas calculadas] devem ser criadas para auxiliar no resumo e na compreensão do comportamento do visitante associado às seguintes métricas:

   * Tempo de redirecionamento médio (Tempo de redirecionamento/Instâncias de tempo de desempenho)
   * Tempo do cache de aplicativos médio (Tempo do cache de aplicativos/Instâncias de tempo de desempenho)
   * Tempo de DNS médio (Tempo de DNS/Instâncias de tempo de desempenho)
   * Tempo de TCP médio (Tempo de TCP/Instâncias de tempo de desempenho)
   * Tempo de solicitação médio (Tempo de solicitação/Instâncias de tempo de desempenho)
   * Tempo de resposta médio (Tempo de resposta/Instâncias de tempo de desempenho)
   * Tempo de processamento médio (Tempo de processamento/Instâncias de tempo de desempenho)
   * Tempo de onLoad médio (Tempo de onLoad/Instâncias de tempo de desempenho)
   * Tempo do carregamento da página médio (Tempo total do carregamento da página/Instâncias de tempo de desempenho)

