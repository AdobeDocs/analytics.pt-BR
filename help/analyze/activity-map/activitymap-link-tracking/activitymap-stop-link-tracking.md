---
description: Etapas para interromper o rastreamento de links no Activity Map ou ClickMap herdado.
seo-description: Etapas para interromper o rastreamento de links no Activity Map ou ClickMap herdado.
seo-title: Parar o rastreamento de links
solution: Analytics
title: Parar o rastreamento de links
topic: Activity Map
uuid: e 17 fb 7 bd-d 6 ed -45 c 3-a 006-9150 d 5718 cff
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Parar o rastreamento de links

Etapas para interromper o rastreamento de links no Activity Map ou ClickMap herdado.

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para interromper o rastreamento de links no... </th> 
   <th colname="col2" class="entry"> Ação... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Remover o conteúdo a seguir do arquivo Appmeasurement.js: 
    <code>/* START Activity Map MODULE O seguinte módulo habilita o rastreamento do Activity Map no Adobe Analytics.O Activity Map permite exibir sobreposições de dados em links e conteúdos para compreender como os usuários interagem com seu site.Se não pretende usar o Activity Map, você pode remover o seguinte bloco de código do arquivo appmeasurement. js.
  Additional documentation on how to configure Activity Map is available at:
      https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function AppMeasurement_Module_Activity Map(g){func
     ...
     /* END Activity Map MODULE */
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (anteriormente conhecido como ClickMap do visitante) </td> 
   <td colname="col2"> <p>Defina a variável <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external">trackInlineStats</a> para falso (esse é o padrão.) The syntax reads as follows: 
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

