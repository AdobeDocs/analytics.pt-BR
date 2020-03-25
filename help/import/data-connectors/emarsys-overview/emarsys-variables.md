---
description: A integração dos Data Connectors para o emarsys usa variáveis do Analytics para rastrear várias métricas do emarsys.
title: Variáveis do Analytics
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variáveis do Analytics {#analytics-variables}

A integração dos Data Connectors para o emarsys usa variáveis do Analytics para rastrear várias métricas do emarsys.

Depois de identificar o evento e as eVars a serem usadas na integração com o emarsys, ative-as no [Admin Console](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/c-admin-tools.html).

**Variáveis obrigatórias**

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variável </th> 
   <th colname="col2" class="entry"> Nome </th> 
   <th colname="col3" class="entry"> Método de preenchimento </th> 
   <th colname="col4" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> evento (numérico) </td> 
   <td colname="col2"> Total de rejeições </td> 
   <td colname="col3"> <p>Importado automaticamente do emarsys </p> </td> 
   <td colname="col4"> <p>O evento Total de rejeições permite que você veja o número de mensagens de email que não foram entregues aos destinatários por causa de um problema de entrega. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> evento (numérico) </td> 
   <td colname="col2"> Clicados </td> 
   <td colname="col3"> <p>Importado automaticamente do emarsys </p> </td> 
   <td colname="col4"> <p>O evento Clicados permite ver o número de visitantes que clicaram na mensagem de email. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> evento (numérico) </td> 
   <td colname="col2"> Abertos </td> 
   <td colname="col3"> <p>Importado automaticamente do emarsys </p> </td> 
   <td colname="col4"> <p>O evento Abertos permite ver o número de visitantes que abriram a mensagem de email. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> evento (numérico) </td> 
   <td colname="col2"> Enviado </td> 
   <td colname="col3"> <p>Importado automaticamente do emarsys </p> </td> 
   <td colname="col4"> <p>O evento Envios permite que você veja o número de mensagens de email enviadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> evento (numérico) </td> 
   <td colname="col2"> Inscrições canceladas </td> 
   <td colname="col3"> <p>Importado automaticamente do emarsys </p> </td> 
   <td colname="col4"> <p>O evento Inscrições canceladas permite que você veja o número de visitantes que abriram o email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email da sua organização. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de destinatário </td> 
   <td colname="col3"> <p>Coletado de parâmetros de consulta em links de email pelo método de coleta automatizada ou por um plug-in JavaScript. </p> </td> 
   <td colname="col4"> ID de destinatário </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar ou s.campaign </td> 
   <td colname="col2"> ID de mensagem </td> 
   <td colname="col3"> <p>Coletado de parâmetros de consulta em links de email pelo método de coleta automatizada ou por um plug-in JavaScript. </p> </td> 
   <td colname="col4"> Esse valor é frequentemente armazenado na variável da campanha. </td> 
  </tr> 
 </tbody> 
</table>

