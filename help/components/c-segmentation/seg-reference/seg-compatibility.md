---
description: Nem todos os segmentos criados no Construtor de segmentos são compatíveis com o Data Warehouse. Essa tabela lista as funções suportadas.
title: Compatibilidade de segmentos de Data Warehouse
topic: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Compatibilidade de segmentos de Data Warehouse

Nem todos os segmentos criados no Construtor de segmentos são compatíveis com o [!DNL Data Warehouse]. Essa tabela lista as funções suportadas.

<table id="table_BBB1DAFDF85041598FA4AF869172CF7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis </th> 
   <th colname="col3" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Exclui</b> </td> 
   <td colname="col2"> Suportado em qualquer nível </td> 
   <td colname="col3"> Suportado somente em casos especiais no nível superior </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segmentos sequenciais</b> </td> 
   <td colname="col2"> Suportado </td> 
   <td colname="col3"> Não suportado </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>E e OU podem ser combinados sem limites</b> </td> 
   <td colname="col2"> Suportado </td> 
   <td colname="col3"> Algumas limitações. Consulte *observação* abaixo da tabela. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Contêineres aninhados</b> </td> 
   <td colname="col2"> Suportado </td> 
   <td colname="col3"> Algumas limitações (elas devem reduzir em escopo, por exemplo, visitantes podem conter ocorrências, mas não o contrário) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensões</b> </td> 
   <td colname="col2">Arraste e solte uma dimensão no campo <span class="uicontrol">Definições</span> do Construtor de segmentos para descobrir mais sobre a compatibilidade do produto. Por exemplo, essas dimensões são suportadas somente na Analysis Workspace, no Reports &amp; Analytics e na Ad Hoc Analysis: 
    <ul id="ul_BD708CC3A16743F49F998D1046EC70A3"> 
     <li id="li_240DA619D50B4336ACD9117BF59AF10A">Servidor de entrada </li> 
     <li id="li_222D4D4116674EF8A52945CCB9C78719">Categoria de entrada </li> 
     <li id="li_5A43C846E2EA4EFCB892DE9E0607C68C">Data de entrada </li> 
     <li id="li_8E9CABBE04FC4A7A9A5D2BDD34AD3C87">Toda a classificação da página de pesquisa </li> 
    </ul> </td> 
   <td colname="col3"> Arraste e solte uma dimensão no campo <span class="uicontrol">Definições</span> do Construtor de segmentos para descobrir mais sobre a compatibilidade do produto. Por exemplo, essas dimensões são suportadas somente no Data Warehouse: 
    <ul id="ul_61A5B314CCCF497DB0385324E3309E22"> 
     <li id="li_1254089BDFAE4E0F8E51CB1511BBBF53">Endereço IP </li> 
     <li id="li_D8E040F77A8C46A084547F4FE685CB10">URL da página </li> 
     <li id="li_4C79AE900CF6458780C124143DC6FA5B">ID de visitante </li> 
     <li id="li_4EC10645DE9740609D8DDFD4F668FE67">ID de visitante da Experience Cloud </li> 
    </ul> <p>As seguintes dimensões <b>não podem</b> ser usadas em segmentos do Data Warehouse: </p> 
    <ul id="ul_FE143F6D1ABF45DAA444E1B5691C7D4F"> 
     <li id="li_E77F3CC45BA04674B857FE5AB19D56F1">Toda a classificação da página de pesquisa </li> 
     <li id="li_95E1549C13F14BA0B32686401EE78E31">AM/PM </li> 
     <li id="li_6F1C8FC2E7674A0CA14B70B65784D896">Dia do mês </li> 
     <li id="li_79D1A91D741D4CCC937D07906D71F964">Dias da semana </li> 
     <li id="li_4008565353084611BD782B98D50C0611">Dia do ano </li> 
     <li id="li_F87D78F125874087BFF74FAAE2BA46F5">Unidade corporativa de entrada </li> 
     <li id="li_53DA4E64C6714CFF90D164245D01C16A">Entrada (Todas as dimensões com Entrada, exceto Página de entrada) </li> 
     <li id="li_7F26B0E54A4A48319F31D8FC499D1CF2">Saída (Todas as dimensões com Saída, exceto Link de saída e Página de saída) </li> 
     <li id="li_1877D2D8A95B43F29CAA426BF2FE4996">Hierarquia (Todas as dimensões com Hierarquia) </li> 
     <li id="li_DF0BCC63ED274ABEA1C5A28274936310">Profundidade de ocorrência </li> 
     <li id="li_98BE56213E1A4FD28D4858D53C46D23E">Tipo de ocorrência </li> 
     <li id="li_52ECB31657DF4180BDB9C8D21CC74313">Hora e Dia </li> 
     <li id="li_93716207F2614822ACB84100B35D27BC">Mês do ano </li> 
     <li id="li_FFC8E1F7092C4876A7E9F2365CC234B9">Páginas não encontradas </li> 
     <li id="li_7A070C8E0F664F5AB554555B17D0E4E6">Pesquisa paga </li> 
     <li id="li_12228C18BF90463C8D8394FB810843D3">Trimestre do ano </li> 
     <li id="li_1833B6E2011C4757A60CAA2C98B35AFA">Frequência de Retorno </li> 
     <li id="li_39154CD74A534D9AA09C701FE1E2C521">Visitas únicas à página </li> 
     <li id="li_84BDE34DD577488881E8842D2DE72D3C">Tempo antes do evento </li> 
     <li id="li_552BE3414CC949B3B24BE99298945874">Tempo gasto na página - No intervalo </li> 
     <li id="li_33D815E04CB3493C82BE33E958C2D7B9">Tempo gasto por visita - Em bucket </li> 
     <li id="li_76F2BB88B8CD456DB50D04F36BB7854B">Motivo da desativação do rastreamento </li> 
     <li id="li_07345E08D0584CEC99128A0542587019">Estados dos Estados Unidos </li> 
     <li id="li_3D6BD9E927334B9BBC29E602D1103F7A">Dia da semana/Fim de semana </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Empilhamento de segmentos</b> </td> 
   <td colname="col2"> Suportado </td> 
   <td colname="col3"> Não suportado </td> 
  </tr> 
 </tbody> 
</table>

*Observação: o Data Warehouse não oferece suporte a todos os casos de uso de um contêiner`exclusion`ou`without`ao usar`AND/OR`. Ao usar essa combinação, somente os segmentos que podem ser regravados como `A AND NOT B` (ou **incluir essa característica** e **excluir essa característica**) são compatíveis com o Data Warehouse.*
