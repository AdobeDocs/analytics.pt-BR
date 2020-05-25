---
description: Etapas para interromper o rastreamento de links no Activity Map ou ClickMap herdado.
title: Interromper o rastreamento de links
topic: Activity map
uuid: e17fb7bd-d6ed-45c3-a006-9150d5718cff
translation-type: ht
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Interromper o rastreamento de links

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
    <code>
     /*
     &nbsp;START&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;The&nbsp;following&nbsp;module&nbsp;enables&nbsp;Activity&nbsp;Map&nbsp;tracking&nbsp;in&nbsp;Adobe&nbsp;Analytics.&nbsp;Activity&nbsp;Map
     &nbsp;allows&nbsp;you&nbsp;to&nbsp;view&nbsp;data&nbsp;overlays&nbsp;on&nbsp;your&nbsp;links&nbsp;and&nbsp;content&nbsp;to&nbsp;understand&nbsp;how
     &nbsp;users&nbsp;engage&nbsp;with&nbsp;your&nbsp;web&nbsp;site.&nbsp;If&nbsp;you&nbsp;do&nbsp;not&nbsp;intend&nbsp;to&nbsp;use&nbsp;Activity&nbsp;Map,&nbsp;you
     &nbsp;can&nbsp;remove&nbsp;the&nbsp;following&nbsp;block&nbsp;of&nbsp;code&nbsp;from&nbsp;your&nbsp;AppMeasurement.js&nbsp;file.
     &nbsp;Additional&nbsp;documentation&nbsp;on&nbsp;how&nbsp;to&nbsp;configure&nbsp;Activity&nbsp;Map&nbsp;is&nbsp;available&nbsp;at:
     &nbsp;https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-admins/activitymap-enable.html
     */
     function&nbsp;AppMeasurement_Module_Activity&nbsp;Map(g){func
     ...
     /*&nbsp;END&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;*/
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (anteriormente conhecido como ClickMap do visitante) </td> 
   <td colname="col2"> <p>Defina a variável <a href="https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/config-vars/configuration-variables.translate.html"  >trackInlineStats</a> para falso (esse é o padrão.) A leitura da sintaxe é realizada da seguinte maneira: 
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

