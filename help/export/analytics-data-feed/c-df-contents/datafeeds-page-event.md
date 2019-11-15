---
description: Tabela de pesquisa para determinar o tipo de um hit com base no valor de page_event.
keywords: Data Feed;page;event;page_event;post_page_event
solution: Analytics
title: Pesquisa de evento da página
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Pesquisa de evento da página

Tabela de pesquisa para determinar o tipo de um hit com base no valor de page_event.

<table id="table_33AF375E0B41474696D7A4A92C652A5F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ocorrência </th> 
   <th colname="col02" class="entry"> valor page_event </th> 
   <th colname="col2" class="entry"> valor post_page_event </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Exibições de página </td> 
   <td colname="col02"> Igual ao posterior </td> 
   <td colname="col2"> <p>0 for all page views ( <code> s.t() </code> calls) </p> <p>0 para chamadas <code> trackState </code> dos SDKs móveis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rastreamento de link </td> 
   <td colname="col02"> <p>10 para "outro link" </p> <p>10 para <code> trackAction </code> e chamadas do ciclo de vida dos SDKs móveis. </p> <p>11 para "link de download" </p> <p>12 para "link externo ou de saída" </p> </td> 
   <td colname="col2"> <p>100 para "outro link" </p> <p>100 para <code> trackAction </code> e chamadas do ciclo de vida dos SDKs móveis. </p> <p>101 para "link de download" </p> <p>102 para "link externo ou de saída" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vídeo Milestone </td> 
   <td colname="col02"> 
    <!--<p>30 - Legacy full media tracking event at the end of the video playback (no longer supported)</p>--> <p>31 – Evento de início de mídia </p> <p>32 – Evento somente de atualização de mídia (não processa qualquer eVar ou outra variável) </p> <p>33 – Evento de atualização de mídia + outra variável (inclui o processamento da eVar e de outra variável) </p> </td> 
   <td colname="col2"> 
    <!--<p> 75 - Legacy full media tracking event at theend of the video playback (no longer supported)</p>--> <p> 76 – Evento de início de mídia </p> <p>77 – Evento somente de atualização de mídia (não processa qualquer eVar ou outra variável) </p> <p>78 – Evento de atualização de mídia + outra variável (inclui o processamento da eVar e de outra variável) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vídeo Heartbeat </p> </td> 
   <td colname="col02"> Igual ao posterior </td> 
   <td colname="col2"> <p> 50 = (não Primetime) Media Stream Start </p> <p> 51 = (não Primetime) Media Stream Close (Concluir/Finalizar) </p> <p> 52 = (não Primetime) Media Stream Scrubbing </p> <p> 53 = (não Primetime) Media Stream Keep Alive </p> <p> 54 = (não Primetime) Media Stream Ad Start </p> <p> 55 = (não Primetime) Media Stream Ad Close (Concluir/Finalizar) </p> <p> 56 = (não Primetime) Media Stream Ad Scrubbing </p> <p> 60 = Primetime Media Stream Start </p> <p> 61 = Primetime Media Stream Close (Concluir/Finalizar) </p> <p> 62 = Primetime Media Stream Scrubbing </p> <p> 63 = Primetime Media Stream Keep Alive </p> <p> 64 = Primetime Media Stream Ad Start </p> <p> 65 = Primetime Media Stream Ad Close (Concluir/Finalizar) </p> <p> 66 = Primetime Media Stream Ad Scrubbing </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pesquisa </td> 
   <td colname="col02"> 40 </td> 
   <td colname="col2"> 80 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Analytics para o Target </td> 
   <td colname="col02"> 70 - Indica uma ocorrência que inclui dados de atividade do Target. Definido como 70 para ocorrências que estão ou não associadas a uma chamada do Analytics. </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

