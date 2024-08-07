---
description: Algumas métricas de visitante do Adobe Analytics e do Adobe Audience Manager apresentam definições semelhantes, mas não são 100% alinhadas por vários motivos.
title: Diferenças na contagem de visitantes
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 85%

---

# Diferenças na contagem de visitantes

Algumas métricas de visitante do Adobe Analytics e do Adobe Audience Manager apresentam definições semelhantes, mas não são 100% alinhadas por vários motivos.

As métricas de visitante são:

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Métrica </th> 
   <th colname="col3" class="entry"> Definição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=pt-BR"  > Adobe Audience Manager: População Total De Segmentos</a> </p> </td> 
   <td colname="col3"> <p>Contagem de dispositivos (Experience Cloud IDs) que eram membros de seu segmento durante o período de lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=pt-BR"  > Adobe Audience Manager: preenchimento de segmentos em tempo real</a> </p> </td> 
   <td colname="col3"> <p>Contagem de dispositivos (Experience Cloud IDs) que eram membros de seu segmento e acessaram suas propriedades durante o período de lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitantes únicos </p> </td> 
   <td colname="col3"> <p>Mostra o número de visitantes únicos que acessaram suas propriedades durante o período de criação do relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitantes com Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Mostra o número de visitantes únicos com uma Experience Cloud ID que acessaram suas propriedades durante o período de criação do relatório. </p> </td> 
  </tr> 
 </tbody> 
</table>

Preenchimento de segmentos do Adobe Audience Manager em tempo real e Visitantes do Analytics com ID de Experience Cloud usada nos relatórios de Audience Analytics serão os mais semelhantes. Entretanto, no futuro, devido a vários fatores, haverá leves discrepâncias entre eles. São fatores contribuidores:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fator </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager: preenchimento de segmentos em tempo real </th> 
   <th colname="col3" class="entry"> Analytics: Visitantes com Experience Cloud ID </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fuso horário </p> </td> 
   <td colname="col2"> <p>UTC (Tempo Universal Coordenado) </p> </td> 
   <td colname="col3"> <p>Especificado por conjunto de relatórios </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtros personalizados </p> </td> 
   <td colname="col2"> <p>Não </p> </td> 
   <td colname="col3"> <p>Sim, por exemplo filtros de IP, filtros de bot </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de 150 segmentos </p> </td> 
   <td colname="col2"> <p>Não </p> </td> 
   <td colname="col3"> <p>Sim - as contagens do Analytics podem ser afetadas em até 5% pelo limite de integração de 150 segmentos. Caso haja truncamento, a mensagem “Limite de público-alvo atingido” será exibida na dimensão Nome de público-alvo. </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulte [Entendendo os segmentos no Analytics e no Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) para explicações adicionais sobre as nuances entre os dados e a segmentação do Analytics e do Audience Manager.
