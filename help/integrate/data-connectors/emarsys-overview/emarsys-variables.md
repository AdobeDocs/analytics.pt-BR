---
description: A integração dos Conectores de dados para emarsys usa variáveis do Analytics para rastrear várias métricas emarsys.
seo-description: A integração dos Conectores de dados para emarsys usa variáveis do Analytics para rastrear várias métricas emarsys.
seo-title: Variáveis do Analytics
title: Variáveis do Analytics
uuid: 4 d 5 e 087 c-f 495-4 aab -9 ad 1-9 b 901 d 34 a 254
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Variáveis do Analytics{#analytics-variables}

A integração dos Conectores de dados para emarsys usa variáveis do Analytics para rastrear várias métricas emarsys.

After identifying the Event and eVars to use with the emarsys integration, enable them in the [Admin Console](https://microsite.omniture.com/t2/help/en_US/reference/index.html?f=conversion_var_admin).

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
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Total de rejeições </td> 
   <td colname="col3"> <p>Importado automaticamente de emarsys </p> </td> 
   <td colname="col4"> <p>O evento Total de rejeições permite ver o número de mensagens de email que não foram entregues aos destinatários devido a um problema de entrega. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Clicado </td> 
   <td colname="col3"> <p>Importado automaticamente de emarsys </p> </td> 
   <td colname="col4"> <p>O evento Clicado permite ver o número de visitantes que clicaram na mensagem de e-mail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Abertos </td> 
   <td colname="col3"> <p>Importado automaticamente de emarsys </p> </td> 
   <td colname="col4"> <p>O evento Aberto permite que você veja o número de visitantes que abriram a mensagem de e-mail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Enviado </td> 
   <td colname="col3"> <p>Importado automaticamente de emarsys </p> </td> 
   <td colname="col4"> <p>O evento Envia permite visualizar o número de mensagens de email enviadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Cancelar inscrição </td> 
   <td colname="col3"> <p>Importado automaticamente de emarsys </p> </td> 
   <td colname="col4"> <p>O evento Cancelar inscrição permite ver o número de visitantes que abriram o email, mas clicaram no link Cancelar inscrição para recusar futuras mensagens de email de sua organização. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>Coletado de parâmetros de consulta em links de email por meio do método de coleta automatizada ou de um plug-in javascript. </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar  ou s. campaign </td> 
   <td colname="col2"> ID da mensagem </td> 
   <td colname="col3"> <p>Coletado de parâmetros de consulta em links de email por meio do método de coleta automatizada ou de um plug-in javascript. </p> </td> 
   <td colname="col4"> Esse valor é armazenado na variável campanha com frequência. </td> 
  </tr> 
 </tbody> 
</table>

