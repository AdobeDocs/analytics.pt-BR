---
description: Na maioria dos casos, você não precisará fazer modificações no código de integração produzido pelo assistente do Conector de dados.
seo-description: Na maioria dos casos, você não precisará fazer modificações no código de integração produzido pelo assistente do Conector de dados.
seo-title: Modificação do código de integração
title: Modificação do código de integração
uuid: 3 f 49 a 29 b-ad 38-4967-894 a-ef 7 ecf 4 d 268 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Modifying the Integration Code{#modifying-the-integration-code}

Na maioria dos casos, você não precisará fazer modificações no código de integração produzido pelo assistente do Conector de dados.

No entanto, se você precisar fazer ajustes, algumas das configurações de código serão descritas abaixo.

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração de código </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.maxDelay </td> 
   <td colname="col2">O número máximo de milissegundos que a solicitação de imagem do Adobe Analytics aguardará pelos dados Demandbase antes de disparar para o servidor de coleção do Analytics. <p>Observação: Essa configuração se aplica em todas as integrações que podem estar sendo executadas por meio do Módulo de integração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._key </td> 
   <td colname="col2"> Sua chave de API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Apiurl </td> 
   <td colname="col2"> O modelo de URL da API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._delim </td> 
   <td colname="col2"> O delimitador usado para separar os valores de dimensão Demandbase quando eles são enviados para o Adobe Analytics. Alterar essa configuração pode fazer com que as Regras de classificação padrão não funcionem corretamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Settnt </td> 
   <td colname="col2">Se verdadeiro, o código de integração tentará usar uma mbox oculta para enviar as dimensões de Demandbase para o Adobe Target como Parâmetros de perfil. <p>Observação: Isso requer que o código mbox. js exista na página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Tntvarprefix </td> 
   <td colname="col2"> Essa string é prefixada para cada nome de dimensão Demandbase antes de enviar para o Adobe Target. Exemplo, se essa configuração tiver o valor «db_», a dimensão «setor» será enviada para o Adobe Target como «db_ industry». </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Dimensionsarray </td> 
   <td colname="col2"> As dimensões padrão Demandbase enviadas para o Adobe Analytics. Recomenda-se que você não modifique essa configuração. A propriedade «max_ size» é o número de caracteres permitidos para a dimensão antes do truncamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Dimensionsarraycustom </td> 
   <td colname="col2"> As dimensões de Demandbase personalizadas enviadas para o Adobe Analytics. A propriedade «max_ size» é o número de caracteres permitidos para a dimensão antes do truncamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Cname </td> 
   <td colname="col2"> O nome do cookie de sessão usado para manter o estado da comunicação de API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Contextname </td> 
   <td colname="col2"> O nome da variável contextdata usada para enviar as dimensões padrão para o Adobe Analytics. Recomenda-se que você não modifique essa configuração. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Contextnamecustom </td> 
   <td colname="col2"> O nome da variável contextdata usada para enviar as dimensões personalizadas para o Adobe Analytics. Recomenda-se que você não modifique essa configuração. </td> 
  </tr> 
 </tbody> 
</table>

