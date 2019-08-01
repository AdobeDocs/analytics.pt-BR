---
description: Descreve as evars e Eventos a serem reservados para cada implementação de conjunto de relatórios.
seo-description: Descreve as evars e Eventos a serem reservados para cada implementação de conjunto de relatórios.
seo-title: Configurar variáveis do Adobe Analytics para Lyris
solution: Analytics
title: Configurar variáveis do Adobe Analytics para Lyris
uuid: 12 e 150 c 4-052 a -481 c -8 c 27-ef 45 ee 801977
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configure Adobe Analytics variables for Lyris{#configure-adobe-analytics-variables-for-lyris}

Descreve as evars e Eventos a serem reservados para cada implementação de conjunto de relatórios.

Essa integração requer pelo menos 2 evars a ser reservado para cada implementação de conjunto de relatórios. Além dessas evars, alguns eventos podem ser reservados, dependendo de quais dados Lyris você gostaria de ver no Analytics. Essas evars e eventos estão descritos na tabela abaixo:

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variável </th> 
   <th colname="col2" class="entry"> Nome da variável </th> 
   <th colname="col3" class="entry"> Como a variável é usada </th> 
   <th colname="col4" class="entry"> Configurações </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID da mensagem </td> 
   <td colname="col3"> Para capturar a identificação de campanha de mensagem de email individual </td> 
   <td colname="col4"> <p>Status: Ativado </p> <p>Alocação: Mais recente </p> <p>Expirar após: «Decisão de negócios» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> Para capturar a identificação anônima para o cliente que clicou na campanha de email </td> 
   <td colname="col4"> <p>Status: Ativado </p> <p>Alocação: Mais recente </p> <p>Expirar após: «Decisão de negócios» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Emails enviados </td> 
   <td colname="col3"> Para armazenar não. de e-mails enviados de Lyris </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Emails abertos </td> 
   <td colname="col3"> Para armazenar não. de e-mails abertos </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Emails únicos abertos </td> 
   <td colname="col3"> Para armazenar não. de e-mails exclusivos abertos </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Click-throughs de email </td> 
   <td colname="col3"> Para armazenar não. de vezes em que qualquer email foi clicado </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Rejeições de email </td> 
   <td colname="col3"> Para armazenar o não. de e-mails que foram removidos </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Cancelar assinatura de email </td> 
   <td colname="col3"> Para armazenar o não. de assinaturas por email desativadas </td> 
   <td colname="col4">Tipo: Numérico <p>Participação: Ativado </p> </td> 
  </tr> 
 </tbody> 
</table>

