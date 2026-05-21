---
description: Algumas métricas de visitante do Adobe Analytics e do Adobe Audience Manager apresentam definições semelhantes, mas não são 100% alinhadas por vários motivos.
title: Diferenças na contagem de visitantes
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
TQID: https://experienceleague.adobe.com/ksfYYDZ6G9vH7WEZVh-JsN93Rl-jsZTe9-CQADSwnfI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 50%

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
   <td colname="col3"> <p>Contagem de dispositivos (Experience Cloud IDs) que eram membros do seu segmento e atingiram suas propriedades durante o período de pesquisa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: visitantes únicos </p> </td> 
   <td colname="col3"> <p>Mostra o número de visitantes únicos que acessaram suas propriedades durante a janela de relatórios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: visitantes com Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Mostra o número de visitantes únicos com uma Experience Cloud ID que atingiram suas propriedades durante a janela de relatórios. </p> </td> 
  </tr> 
 </tbody> 
</table>

Preenchimento de segmentos do Adobe Audience Manager em tempo real e Visitantes do Analytics com Experience Cloud ID usados em relatórios do Audience Analytics serão os mais semelhantes. Para o curto prazo, no entanto, devido a vários fatores, haverá pequenas discrepâncias entre eles. Os fatores que contribuem são:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fator </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager: preenchimento de segmentos em tempo real </th> 
   <th colname="col3" class="entry"> Analytics: visitantes com Experience Cloud ID </th> 
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
   <td colname="col3"> <p>Sim, por exemplo, filtros IP, filtros de bot </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de 150 segmentos </p> </td> 
   <td colname="col2"> <p>Não </p> </td> 
   <td colname="col3"> <p>Sim - as contagens do Analytics podem ser afetadas em até 5% pelo limite de integração de 150 segmentos. Caso haja truncamento, a mensagem “Limite de público-alvo atingido” será exibida na dimensão Nome de público-alvo. </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulte [Entendendo os segmentos no Analytics e no Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) para explicações adicionais sobre as nuances entre os dados e a segmentação do Analytics e do Audience Manager.
