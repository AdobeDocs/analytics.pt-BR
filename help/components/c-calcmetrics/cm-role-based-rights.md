---
description: Os direitos das métricas calculadas são diferentes para usuários de nível administrativo e não administrativos.
title: 'Métricas calculadas: direitos baseados em função'
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '251'
ht-degree: 100%

---

# Métricas calculadas: direitos baseados em função

Os direitos das métricas calculadas são diferentes para usuários de nível administrativo e não administrativos.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> Criar </th> 
   <th colname="col2" class="entry"> Compartilhar </th> 
   <th colname="col3" class="entry"> Exibir/gerenciar </th> 
   <th colname="col4" class="entry"> Aprovar </th> 
   <th colname="col5" class="entry"> Aplicar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Usuários de nível administrativo</b> </td> 
   <td colname="col02"> Os administradores podem criar métricas calculadas e Perfis de produto no Admin Console para limitar os direitos de usuários de criar métricas calculadas. </td> 
   <td colname="col2"> Podem compartilhar com toda a empresa, com grupos de usuários e usuários individuais. </td> 
   <td colname="col3"> <span class="keyword"> Reports &amp; Analytics</span>: podem exibir/editar/excluir/etc. suas próprias métricas calculadas e as de outros usuários. <p> <span class="keyword"> Report Builder </span>: pode exibir/editar/excluir/etc. suas próprias métricas calculadas e as compartilhadas. </p> </td> 
   <td colname="col4"> Podem aprovar métricas calculadas como canônicas. </td> 
   <td colname="col5"> Podem aplicar métricas calculadas em toda a organização. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Usuários de nível não administrativo</b> </td> 
   <td colname="col02"> Por padrão, os usuários podem criar métricas calculadas. No entanto, esses direitos podem ser limitados por administradores. </td> 
   <td colname="col2"> Podem compartilhar somente com usuários individuais </td> 
   <td colname="col3"> É possível visualizar/editar/excluir/etc. somente suas próprias métricas calculadas. <p>Usuários não administrativos devem ter acesso a todos os eventos de componente para poderem ver métricas compartilhadas (as permissões no Admin Console ainda se aplicam). </p> <p>Se um relatório agendado ou painel for compartilhado com um usuário não administrativo e a métrica não estiver compartilhada com ele, o relatório será executado com a métrica aplicada (assumindo que o usuário tenha permissões para exibir eventos). Contudo, o usuário não poderá ver a definição ou editar a métrica. </p> </td> 
   <td colname="col4"> Só podem utilizar métricas calculadas aprovadas; não podem marcar métricas como aprovadas. </td> 
   <td colname="col5"> Podem aplicar suas próprias métricas calculadas e segmentos que foram compartilhados com eles. </td> 
  </tr> 
 </tbody> 
</table>
