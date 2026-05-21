---
description: O Report Builder usa o calendário personalizado do Analytics. Você pode usar o calendário para definir o primeiro dia da semana e ano, ou usar um estilo de calendário de varejo diferente. Os formatos de calendário são usados para várias finalidades, incluindo comparação de vendas e padronização de previsão, análise de custo de folha de pagamento ou regulamento de contagem de inventário físico.
title: Calendário personalizado
feature: Report Builder
role: User, Admin
exl-id: e65cb6c8-8bb0-4dcd-a3a3-d22adcd024fa
TQID: https://experienceleague.adobe.com/At3YiOPV0jx5WXwe-VvA05n3yIEmiAJIRzoOoeISeA4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 30%

---

# Calendário personalizado

{{legacy-arb}}

O Report Builder usa o calendário personalizado do Analytics. Você pode usar o calendário para definir o primeiro dia da semana e ano, ou usar um estilo de calendário de varejo diferente. Os formatos de calendário são usados para várias finalidades, incluindo comparação de vendas e padronização de previsão, análise de custo de folha de pagamento ou regulamento de contagem de inventário físico.

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
   <td colname="col1"> <p>Calendário gregoriano </p> </td> 
   <td colname="col2"> <p> Usa o formato de calendário tradicional (janeiro a dezembro, com 30 ou 31 dias e um número variável de semanas em cada mês). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendário Gregoriano Modificado </p> </td> 
   <td colname="col2"> <p> Usa o Calendário gregoriano tradicional, mas permite selecionar o primeiro mês do ano e o primeiro dia da semana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4-5-4 Calendário fiscal </p> </td> 
   <td colname="col2"> <p> Divide cada mês pelo número de semanas no mês. Janeiro tem quatro semanas, e assim por diante. A National Retail Federation usa o formato de calendário 4-5-4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendário personalizado </p> </td> 
   <td colname="col2"> <p> Oferece três formatos com base no número de semanas em cada mês. O número de semanas em cada mês depende do primeiro dia do ano selecionado. </p> <p>Um ano tem 52 semanas. Divida isso em 4 trimestres e você terá 13 semanas por trimestre. Mas há 3 meses em um trimestre. O número 13 não é divisível por três, dessa forma você acaba colocando uma semana extra em um dos meses, de forma que seja sempre consistente. 5/4/4 significa que o primeiro mês do trimestre recebe a semana extra. 4/5/4 significa que o segundo mês do trimestre recebe a semana extra, etc. No calendário 5-4-4, a 53ª semana é adicionada ao último trimestre do ano. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>:Janeiro tem quatro semanas, fevereiro tem cinco semanas, março tem quatro semanas e assim por diante. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: janeiro tem quatro semanas, fevereiro tem quatro semanas, março tem cinco semanas e assim por diante. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>: janeiro tem cinco semanas, fevereiro tem cinco semanas, março tem quatro semanas e assim por diante. </li> 
    </ul> <p>Observação: essa opção de calendário é compatível com todas as ferramentas do Adobe Analytics: Analysis Workspace, Report Builder e Activity Map. A exceção é o Data Warehouse, que não oferece suporte a calendários personalizados. </p> </td> 
  </tr> 
 </tbody> 
</table>
