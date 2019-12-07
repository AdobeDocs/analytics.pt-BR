---
description: O construtor de relatórios usa o calendário personalizado do Analytics. Você pode usar o calendário para definir o primeiro dia da semana e ano, ou usar um estilo de calendário de varejo diferente. Os formatos de calendário são usados para várias finalidades, inclusive comparações de vendas e padronização de previsões, análise de custos com folha de pagamento ou regulamento de contagem de inventário físico.
title: Calendário personalizado
topic: Report builder
uuid: 88d24bf9-de46-41e0-937e-b8a1fe36c55d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Calendário personalizado

O construtor de relatórios usa o calendário personalizado do Analytics. Você pode usar o calendário para definir o primeiro dia da semana e ano, ou usar um estilo de calendário de varejo diferente. Os formatos de calendário são usados para várias finalidades, inclusive comparações de vendas e padronização de previsões, análise de custos com folha de pagamento ou regulamento de contagem de inventário físico.

Cada um dos formatos de calendário é descrito abaixo.

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calendário </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Calendário Gregoriano </p> </td> 
   <td colname="col2"> <p> Use o formato de calendário tradicional (janeiro a dezembro com 30 ou 31 dias e um número variável de semanas em cada mês). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendário Gregoriano Modificado </p> </td> 
   <td colname="col2"> <p> Usa o calendário gregoriano tradicional, mas permite que você selecione o primeiro mês do ano e o primeiro dia da semana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendário de varejo 4-5-4 </p> </td> 
   <td colname="col2"> <p> Desmembra cada mês pelo número de semanas no mês. Isto é, janeiro tem quatro semanas, e assim por diante. A Federação Nacional do Varejo nos Estados Unidos usa o formato de calendário 4-5-4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendário personalizado </p> </td> 
   <td colname="col2"> <p> Oferece três formatos baseados no número de semanas em cada mês. O número de semanas em cada mês depende do primeiro dia do ano selecionado. </p> <p>Um ano possui 52 semanas. Divida esse valor por 4 trimestres e você terá 13 semanas por trimestre. Mas há 3 meses em um trimestre. O número 13 não é divisível por três, dessa forma você acaba colocando uma semana extra em um dos meses, de forma que seja sempre consistente. 5-4-4 significa que o primeiro mês do trimestre recebe a semana extra. 4-5-4 significa que o segundo mês do trimestre recebe a semana extra, etc. No calendário 5-4-4, a 53ª semana é adicionada ao último trimestre do ano. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>: janeiro possui quatro semanas, fevereiro cinco, março quatro e assim por diante. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: janeiro possui quatro semanas, fevereiro quatro, março cinco e assim por diante. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>: janeiro possui cinco semanas, fevereiro cinco, março quatro e assim por diante. </li> 
    </ul> <p>Observação: essa opção de calendário é suportada em todas as ferramentas do Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, Report Builder, Activity Map, Ad Hoc Analysis) exceto para Data Warehouse, que não tem suporte a calendários personalizados. </p> </td> 
  </tr> 
 </tbody> 
</table>

