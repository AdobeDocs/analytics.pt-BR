---
description: O plug-in s.hitGovernor rastreia o número total de solicitações de imagem do Analytics enviadas durante um intervalo de tempo predefinido e pode executar lógica adicional, se necessário, caso esse total exceda um determinado limite.
seo-description: O plug-in s.hitGovernor rastreia o número total de solicitações de imagem do Analytics enviadas durante um intervalo de tempo predefinido e pode executar lógica adicional, se necessário, caso esse total exceda um determinado limite.
seo-title: hitGovernor
title: hitGovernor
uuid: d 9091 eae -005 a -43 c 2-b 419-980 b 795 bc 2 a 9
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# hitGovernor

O plug-in s.hitGovernor rastreia o número total de solicitações de imagem do Analytics enviadas durante um intervalo de tempo predefinido e pode executar lógica adicional, se necessário, caso esse total exceda um determinado limite.

## hitGovernor {#topic_56B636A42A624B38A0A446C607ACD700}

O plug-in s.hitGovernor rastreia o número total de solicitações de imagem do Analytics enviadas durante um intervalo de tempo predefinido e pode executar lógica adicional, se necessário, caso esse total exceda um determinado limite.

Embora o tráfego de bots, spiders, agentes de usuário específicos ou de uma lista específica de endereços IP possa ser identificado como tráfego de bot ou de outra forma excluído dos relatórios, algum tráfego que não deveria ser contabilizado poderá ser capturado nos conjuntos de relatórios. Por exemplo, um grande número de cliques ou exibições de página durante um período irrazoável (ou seja, aproximadamente uma solicitação por segundo) poderia ser tráfego duplicado.

A utilização desse plug-in permite o bloqueio automático desse tráfego para o restante da vida útil do visitante, e esse tráfego também pode ser identificado dinamicamente nos relatórios.

## Como funciona o plug-in HitGovernor {#section_541BC639E31442D09B1C85A2FFCDC02C}

O plug-in incrementa um valor de cookie cada vez que uma solicitação de imagem é enviada para os servidores de rastreamento e rastreia ao longo de um intervalo de tempo contínuo. O intervalo de tempo padrão é de um minuto, embora possa ser substituído. (Consulte [Implementação](../../../implement/js-implementation/plugins/hitgovernor.md#task_D4BDB524AA294C139AFCAE2B61FEA3F2) abaixo). If the total number of hits during that time frame exceeds the default hit threshold (60), a final custom link image request is sent to set the *`exceptionFlag`* context data variable. O limite de hit padrão também pode ser substituído.

Se desejado, a partir desse ponto, o tráfego pode ser impedido de ser coletado para esse visitante específico por um período padrão de sessenta dias. Bloquear o tráfego exige uma linha adicional de código na função doPlugins, conforme descrito abaixo. O intervalo de tempo também pode ser ajustado. The logic allows time to either include that visitor's IP address, User Agent, or [!DNL Experience Cloud] Visitor ID in the proper permanent exception logic, or to reset the timeout period after the sixty days have elapsed. Se esse tráfego for identificado como fraudulento pelo plug-in após sessenta dias, ele será sinalizado novamente como uma exceção e não será coletado por mais sessenta dias.

## Relatório {#section_E742F19B528041808454744DB2C7007C}

Nenhuma variável ou evento padrão precisa ser definido. No entanto, recomendamos que você configure a lógica das regras de processamento para definir variáveis e eventos de acordo. Essas variáveis e eventos personalizados podem incluir:

* [!DNL Experience Cloud] ID de visitante
* Endereço IP
* Agente do usuário
* Evento de exceção sinalizado

A criação de segmentos para essas variáveis permite criar segmentos e conjuntos de relatórios virtuais para exibir o impacto geral desses hits ambíguos no site.

Recomendamos usar os valores capturados no relatório para atualizar as regras de bot, as regras de DB VISTA ou as exclusões de IP da empresa.

## Implementação {#task_D4BDB524AA294C139AFCAE2B61FEA3F2}

Para implementar o plug-in hitGovernor:

1. Modificar a biblioteca do AppMeasurement.

   Para inicializar o plug-in, inclua essa linha de código (em negrito) na função `registerPostTrackCallback` no código de biblioteca do AppMeasurement.

   >[!NOTE]
   >
   >Although the `registerPostTrackCallback` functionality is included in AppMeasurement libraries 1.8.0+, it is not included in any custom code configuration by default. Ela é incluída após e *fora da* função doPlugins.

   ```
    s.registerPostTrackCallback(function(){ 
       
<b> s.governor();</b> 
   });
   ```

   Below the doPlugins section of your AppMeasurement file, include the plugin code contained in [Plugin Source Code](../../../implement/js-implementation/plugins/hitgovernor.md#reference_76423C81A7A342B2AC4BE41490B27DE0), below.

   The hit limit threshold, hit timing threshold, and traffic exclusion time frames can all be overridden by setting these variables, outside of the plugin itself and preferably with your other configuration variables:

<table id="table_9959A40F5F0B40B39DB86E21D03E25FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Syntax </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Hit Limit Threshold </p> </td> 
   <td colname="col2"> <p> <code> s.hl = 60; </code> </p> </td> 
   <td colname="col3"> <p>The total number of hits that should not be exceeded during a given timeframe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hit Time Threshold </p> </td> 
   <td colname="col2"> <p> <code> s.ht = 10; </code> </p> </td> 
   <td colname="col3"> <p>The window, in seconds, for when hits are recorded. This number is divided by six to determine the rolling timing windows. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclusion Threshold </p> </td> 
   <td colname="col2"> <p> <code> s.he = 60; </code> </p> </td> 
   <td colname="col3"> <p>Number of days that the exclusion cookie is set for that visitor. </p> </td> 
  </tr> 
 </tbody> 
</table>

   >[!NOTE]
   >
   >Your implementation might use a different object name than the default analytics "s" object. If so, please update the object name accordingly.

1. Configure processing rules.

   This plugin records flagged exceptions as context data in a link tracking image request. As such, processing rules must be configured to assign track those flagged exceptions into appropriate variables like those below.

   ![](assets/hitgov-config.png)

1. (Optional) Include the traffic-blocking code in doPlugins.

   After traffic has been identified as an exception, any subsequent hits from that visitor can be blocked entirely by including this code within the `doPlugins` function:

   ```
   //Check for hit governor flag 
         if(s.Util.cookieRead('s_hg')==9)s.abort=true;
   ```

   If this code is not included, traffic from that visitor will be flagged but not blocked. 

## Plugin Source Code {#reference_76423C81A7A342B2AC4BE41490B27DE0}

This code should be added below the doPlugins section of your AppMeasurement library.

```
//Hit Governor (Version 0.1 BETA, 11-13-17) 
s.governor=new Function("","" 
+"var s=this;if(typeof s.hl=='undefined'){s.hl=60;}if(typeof s.ht=='u" 
+"ndefined'){s.ht=60;}if(typeof s.he=='undefined'){s.he=60;}if(s.Util" 
+".cookieRead('s_hg')==8){var i=new Date(),y=i.getFullYear(),m=i.getM" 
+"onth(),d=i.getDate(),i=new Date(y,m,d+s.he);s.Util.cookieWrite('s_h" 
+"g',9,i);return;}var f=s.Util.cookieRead('s_hc'),g=Number(s.Util.coo" 
+"kieRead('s_ht')),h=Math.floor((new Date()).getTime()),ha=f!=''?f.sp" 
+"lit('|').map(Number):[0,0,0,0,0],i=ha.reduce(function(ha,b){return " 
+"ha+b;},0),j=g==0?0:Math.floor(((h-g)/(s.ht/6))/1000);if(g==0)s.Util" 
+".cookieWrite('s_ht',h);if(i<s.hl){if(j>=1){if(j>=6){ha=[0,0,0,0,0];" 
+"}else{for(var k=0;k<j;k++){ha.unshift(0);ha.pop();}}s.Util.cookieWr" 
+"ite('s_ht',h);}}else{s.Util.cookieWrite('s_hg',8);s.linkTrackVars+=" 
+"',contextData.exceptionFlag';s.contextData['exceptionFlag']='true';" 
+"s.tl(this,'o','exceptionFlag');}ha[0]++;s.Util.cookieWrite('s_hc',h" 
+"a.join('|'));"); 

```

