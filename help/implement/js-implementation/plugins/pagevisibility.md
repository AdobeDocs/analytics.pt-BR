---
description: Registra por quantos segundos a página foi a guia ativa no navegador e passa o valor para uma métrica na próxima exibição de página.
keywords: Implementação do Analytics
seo-description: Registra por quantos segundos a página foi a guia ativa no navegador e passa o valor para uma métrica na próxima exibição de página.
seo-title: getPageVisibility
solution: Analytics
title: getPageVisibility
topic: Desenvolvedor e implementação
uuid: 3891 e 2 aa-d 5 c 1-4 a 2 b -8522-eb 2 bae 39 ea 2 e
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPageVisibility

Registra por quantos segundos a página foi a guia ativa no navegador e passa o valor para uma métrica na próxima exibição de página.

>[!NOTE]
>
>Esta é uma versão beta do plug-in e pode haver atualizações adicionais.

This plug-in requires [getVisitStart](../../../implement/js-implementation/plugins/getvisitstart.md#concept_1C3CD25A87094A498A1D8A455963FBD8).

Este plug-in também registra o total de segundos em que a página esteve no navegador (tempo de exibição ativo e passivo). É necessário utilizar o plug-in getPreviousValue para rastrear o nome da página anterior associado aos eventos de visibilidade da página. O rastreamento desses valores ajuda você a entender melhor a participação do visitante e a rastrear com mais precisão o comportamento do visitante nos sites.

É necessário utilizar o plug-in getPreviousValue para rastrear o nome da página anterior associado aos eventos de visibilidade da página. O rastreamento desses valores ajuda você a entender melhor a participação do visitante e a rastrear com mais precisão o comportamento do visitante nos sites.

>[!NOTE]
>
>As instruções a seguir exigem que você altere o código de coleta de dados do site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do Analytics. This plug-in is compatible only with [!DNL AppMeasurement] tracking libraries.

## Plug-ins de suporte obrigatórios {#section_0CA7624F4A7B4B5F851A4300937887AD}

* appendList
* getPreviousValue
* getVisitStart

## Código e implementação do plug-in {#section_543ABD8B3E6A48A5AFD86CFEDE144696}

**Seção de configuração**

A variável `s.pvel` deve conter os três eventos que você deseja utilizar:

| Evento | Definição |
|---|---|
| Total de segundos de visibilidade da página (numérico) | O tempo total em que a página esteve ativa no navegador |
| Total de segundos da página (numérico) | O tempo total em que a página esteve carregada no navegador, independentemente do estado de visibilidade |
| Total de instâncias de visibilidade da página (contador) | O número total de vezes que um valor foi registrado nos dois eventos anteriores |

**Solicitações de exemplo**

```
//Page Visibility Event List (total page visibility seconds, total page seconds, total page visibility instances) 
s.pvel='event7,event8,event9' 
```

**Seção doPlugins**

Para inicializar o plug-in, é necessário utilizar duas linhas de código na seção `doPlugins` do s_code, preferencialmente depois de designar a variável `s.pageName`.

**Solicitações de exemplo**

```
/* Page Visibility */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.getPageVisibility(); 
```

**Seção de plug-ins**

```
/* Page Visibility Plugin 0.1 (BETA) */ 
s.getPageVisibility=new Function("","" 
+"var s=this;if(s.getVisitStart()){s.Util.cookieWrite('s_pvs','');s.U" 
+"til.cookieWrite('s_tps','');}if(s.Util.cookieRead('s_pvs')&&s.pvt<1" 
+"){if(parseInt(s.Util.cookieRead('s_pvs'))<=parseInt(s.Util.cookieRe" 
+"ad('s_tps'))){s.pve=s.pvel.split(',');s.events=s.apl(s.events,s.pve" 
+"[0]+'='+(parseInt(s.Util.cookieRead('s_pvs'))),',',2);s.Util.cookie" 
+"Write('s_pvs','');s.events=s.apl(s.events,s.pve[1]+'='+(parseInt(s." 
+"Util.cookieRead('s_tps'))),',',2);s.Util.cookieWrite('s_tps','');s." 
+"events=s.apl(s.events,s.pve[2],',',2);}}s.pvi=setInterval(s.pvx,100" 
+"0);s.wpvi=setInterval(s.wpvc,5000);"); 
s.gbp=new Function("","" 
+"if('hidden'in document){return null;}var bp=['moz','ms','o','webkit" 
+"'];for(var i=0;i<bp.length;i++){var p=bp[i]+'Hidden';if(p in docume" 
+"nt){return bp[i];}}return null;"); 
s.hp=new Function("p","" 
+"if(p){return p+'Hidden';}else{return'hidden';}"); 
s.vs=new Function("p","" 
+"if(p){return p+'VisibilityState';}else{return'visibilityState';}"); 
s.ve=new Function("p","" 
+"if(p){return p+'visibilitychange';}else{return'visibilitychange';}"); 
s.pvx=new Function("","" 
+"s.pvt+=1;"); 
s.wpvc = function(){var tempDate = Date.now();s.Util.cookieWrite('s_tps', 
Math.ceil((tempDate - s.totalTime)/1000));s.Util.cookieWrite('s_pvs', s.pvt)} 
document.addEventListener('visibilitychange',function(event){if(document.hidden){s.visibility = false;clearTimeout(s.pvi);}else{s.visibility=true;s.pvi=setInterval(s.pvx,1000);}});s.totalTime=new Date();s.pvt=0;s.prefix=s.gbp;s.hidden=s.hp(s.prefix);s.visibility=true;s.visibilityState=s.vs(s.prefix);s.visibilityEvent=s.ve(s.prefix); 
```

## Notas {#section_47964BB9D0A24BFEB4B2498A41D8B017}

* Sempre teste as instalações de plug-ins para garantir que a coleta de dados ocorra como esperado antes de ser implantada em um ambiente de produção.
* Como o plug-in envia os segundos de visibilidade da página e o total de segundos à medida que são associados à página anterior, os dados são coletados para a exibição de página final da visita.
* Esse plug-in depende da capacidade de definir cookies no navegador da Web do usuário. Se o usuário não aceitar cookies primários, então o plug-in não passará dados para o Analytics.
* The plug-in creates its own first-party cookies named `s_tps` and `s_pvs`.

* Um percentual muito pequeno de usuários não enviará o percentual dos dados exibidos na página devido às limitações do navegador, e a lógica é contida no plug-in para garantir que os dados não sejam desviados como resultado. No entanto, esse plug-in foi testado com êxito no IE, Firefox, Chrome e Safari.
* Devido à forma como o plug-in avalia o total de segundos e associa esse valor ao nome da página anterior, existirão diferenças entre o tempo padrão gasto em métricas de página e as métricas de total de segundos.
* [!UICONTROL As métricas calculadas] podem ser criadas para auxiliar no resumo e compreensão do comportamento do visitante associado a essas métricas:

   * ** Proporção de visibilidade da página** (Total de segundos de visibilidade da página/Total de segundos da página)
   * ** Total de segundos oculto** (Total de segundos da página - Total de segundos de visibilidade da página)
   * ** Média de segundos de visibilidade da página** (Total de segundos de visibilidade da página/Total de instâncias de visibilidade da página)
   * **Média de segundos de página oculta** ((Total de segundos da página - Total de segundos de visibilidade da página)/Total de instâncias de visibilidade da página)

* Devido à forma como o plug-in soma os segundos, pode existir uma diferença de 1 a 2 segundos entre o total de segundos de visibilidade da página e o total de segundos, como o total de segundos sendo o maior. (Será solucionado em uma atualização futura)
* O uso do plug-in getVisitStart deve contabilizar os visitantes que têm um novo início de visita após um período de mais de 30 minutos de inatividade. Isto não está funcionando como programado; no entanto, provavelmente haverá uma solução ao incorporar o "total de segundos ativos" em uma iteração futura do plug-in.

## Perguntas frequentes {#section_1ED9391D3BAA4208817F0DF69ABBB25E}

**Este plug-in faz chamadas de servidor adicionais? **

O plug-in registrará somente os valores de visibilidade da página em chamadas de servidor da exibição de página subsequente. Nenhuma chamada de servidor adicional será utilizada com isso.

**Se eu não desejar captar as instâncias de total de segundos da página ou visibilidade total da página, é possível omiti-las da lista de eventos? **

Sim, as instâncias de total de segundos da página e visibilidade total da página são eventos opcionais e podem ser omitidos da lista, se desejado.

**Os eventos captados fazem sentido se eu utilizá-los em relatórios diferentes do Nome da página anterior? **

Como o plug-in registra valores na solicitação de imagem subsequente, é possível aplicar somente outras eVars captadas em um contexto de "página anterior", isto é, "URL da página anterior".

**O plug-in enviará o tempo de visibilidade em uma solicitação de s.tl() ou somente em uma solicitação de s.t()?**

O tempo de visibilidade é registrado somente com as solicitações de s.t().
