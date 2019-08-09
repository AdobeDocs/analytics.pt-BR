---
description: Essa integração requer 2 evars a serem reservadas para cada implementação de conjunto de relatórios.
seo-description: Essa integração requer 2 evars a serem reservadas para cada implementação de conjunto de relatórios.
seo-title: Configurar variáveis do Analytics para seleção
solution: Analytics
title: Configurar variáveis do Analytics para seleção
uuid: 3 b 7 b 8 b 4 b -7614-4439-bcb 0-dbdec 5304844
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Configurar variáveis do Analytics para seleção{#configure-analytics-variables-for-selligent}

Essa integração requer 2 evars a serem reservadas para cada implementação de conjunto de relatórios.

Além dessas evars, alguns eventos podem ser reservados dependendo dos dados de Selligent, que você gostaria de ver no Analytics. Essas evars e eventos são descritos como abaixo:

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variável </th> 
   <th colname="col2" class="entry"> Nome da variável </th> 
   <th colname="col3" class="entry"> Como é usado </th> 
   <th colname="col4" class="entry"> Configurações </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID da mensagem </td> 
   <td colname="col3"> Para capturar a identificação de campanha de mensagem de email individual. </td> 
   <td colname="col4"> <p><b>Status</b>: Ativado </p> <p><b>Alocação</b>: Mais recente </p> <p><b>Expirar após</b>: «Decisão de negócios» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> Para capturar a identificação anônima para o cliente que clicou na campanha de email. </td> 
   <td colname="col4"> <p><b>Status</b>: Ativado </p> <p><b>Alocação</b>: Mais recente </p> <p><b>Expirar após</b>: «Decisão de negócios» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Enviado </td> 
   <td colname="col3"> Para armazenar o número de e-mails enviados de Selligent. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Entregue </td> 
   <td colname="col3"> Para armazenar o número de emails entregues. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Exibições </td> 
   <td colname="col3"> Para armazenar o número de e-mails únicos que foram visualizados. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Cliques </td> 
   <td colname="col3"> Para armazenar o número de vezes que qualquer email foi clicado. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Ignorado </td> 
   <td colname="col3"> Para armazenar o número de emails que foram removidos. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participação</b>: Ativado </p> </td> 
  </tr> 
 </tbody> 
</table>

