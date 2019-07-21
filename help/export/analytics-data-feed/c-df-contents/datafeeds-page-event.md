---
description: Tabela de pesquisa para determinar o tipo de um hit com base no valor de page_event.
keywords: Feed de dados; página; evento; page_ event; post_ page_ event
seo-description: Tabela de pesquisa para determinar o tipo de um hit com base no valor de page_event.
seo-title: Pesquisa do evento da página
solution: Analytics
title: Pesquisa do evento da página
topic: Reports and Analytics
uuid: 73 af 597 c -5560-466 e -94 b 2-ddd 1 d 64797 c 8
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Pesquisa do evento da página

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
   <td colname="col2"> <p>0 para todas as exibições de página (chamadas <code>s.t()</code>) </p> <p>0 para chamadas <code>trackState</code> dos SDKs móveis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rastreamento de link </td> 
   <td colname="col02"> <p>10 para "outro link" </p> <p>10 para <code>trackAction</code> e chamadas do ciclo de vida dos SDKs móveis. </p> <p>11 para "link de download" </p> <p>12 para "link externo ou de saída" </p> </td> 
   <td colname="col2"> <p>100 para "outro link" </p> <p>100 para <code>trackAction</code> e chamadas do ciclo de vida dos SDKs móveis. </p> <p>101 para "link de download" </p> <p>102 para "link externo ou de saída" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vídeo Milestone </td> 
   <td colname="col02"> 
    <!--<p>30 - Legacy full media tracking event at the end of the video playback (no longer supported)</p>--> <p>31 – Evento de início de mídia </p> <p>32 - Evento somente de atualização de mídia (não executa nenhum evar ou outra variável) </p> <p>33 – Evento de atualização de mídia + outra variável (inclui o processamento da eVar e de outra variável) </p> </td> 
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

