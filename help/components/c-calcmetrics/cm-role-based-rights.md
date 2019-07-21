---
description: Os direitos das métricas calculadas são diferentes para usuários de nível administrativo e não administrativos.
seo-description: Os direitos das métricas calculadas são diferentes para usuários de nível administrativo e não administrativos.
seo-title: Direitos de métricas calculadas com base em funções
title: Direitos de métricas calculadas com base em funções
uuid: 7 c 14 d 32 d -370 c -4 afa -8 f 80-5 bbd 8 fc 12 ec 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Métricas calculadas: direitos baseados em função

Os direitos das métricas calculadas são diferentes para usuários de nível administrativo e não administrativos.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> Criar  </th> 
   <th colname="col2" class="entry"> Compartilhar </th> 
   <th colname="col3" class="entry"> Exibir/gerenciar </th> 
   <th colname="col4" class="entry"> Aprovar </th> 
   <th colname="col5" class="entry"> Aplicar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Usuários de nível administrativo</b> </td> 
   <td colname="col02"> Os administradores podem criar métricas calculadas e <a href="https://marketing.adobe.com/resources/help/en_US/reference/groups.html" format="https" scope="external">grupos</a> para limitar os direitos do usuário de criar métricas calculadas. </td> 
   <td colname="col2"> Podem compartilhar com toda a empresa, com grupos de usuários e usuários individuais. </td> 
   <td colname="col3"> <span class="keyword"> [! Relatórios e análises UICONTROL] </span>: Pode exibir/editar/excluir/etc. suas próprias métricas calculadas e as de outros usuários. <p> <span class="keyword"> Ad Hoc Analysis</span> e <span class="keyword">Report Builder</span>: podem exibir/editar/excluir/etc. suas próprias métricas calculadas e aquelas compartilhadas com eles. </p> </td> 
   <td colname="col4"> Podem aprovar métricas calculadas como canônicas. </td> 
   <td colname="col5"> Podem aplicar métricas calculadas em toda a organização. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Usuários de nível não administrativo</b> </td> 
   <td colname="col02"> Por padrão, os usuários podem criar métricas calculadas. No entanto, esses direitos podem ser limitados por administradores. </td> 
   <td colname="col2"> Podem compartilhar somente com usuários individuais </td> 
   <td colname="col3"> Podem visualizar/editar/excluir/etc. somente suas próprias métricas calculadas. <p>Usuários não administrativos devem ter acesso a todos os eventos de componente para poderem ver métricas compartilhadas (as permissões no Admin Console ainda se aplicam). </p> <p>Se um relatório programado ou painel for compartilhado com um usuário não administrativo e a métrica não estiver compartilhada com ele, o relatório será executado com a métrica aplicada (assumindo que o usuário tenha permissões para exibir eventos). Contudo, o usuário não poderá ver a definição ou editar a métrica. </p> </td> 
   <td colname="col4"> Só podem utilizar métricas calculadas aprovadas; não podem marcar métricas como aprovadas. </td> 
   <td colname="col5"> Podem aplicar suas próprias métricas calculadas e segmentos que foram compartilhados com eles. </td> 
  </tr> 
 </tbody> 
</table>

