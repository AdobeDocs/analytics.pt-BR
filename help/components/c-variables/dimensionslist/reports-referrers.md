---
description: Mostra o domínio ou URL de onde os visitantes vieram antes de chegarem ao site, os métodos utilizados para encontrar site e o número de visitas ao site que vieram desses locais de referência.
title: Referenciadores
topic: Reports
uuid: e63b47b4-49f3-43af-8409-3272bec0484e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Referenciadores

Mostra o domínio ou URL de onde os visitantes vieram antes de chegarem ao site, os métodos utilizados para encontrar site e o número de visitas ao site que vieram desses locais de referência.

Por exemplo, se um visitante clica em um link do Site A e chega do site, Site A é o referenciador se não for definido como parte de seu domínio. Durante a implementação, o seu consultor de implementação pode ajudá-lo a definir os domínios e os URLs que fazem parte do site. (Essa alteração pode ser feita após a implementação.)

Os domínios ou URLs que não façam parte desses domínios e URLs definidos são considerados referenciadores. Por exemplo, se a página da Web A e a página da Web B são adicionadas ao filtro interno de URL, mas a página da Web C não é. Nesse caso, a página da Web C é considerada um referenciador.

## Alocação, expiração e valores especiais {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reports &amp; Analytics de marketing (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Análise ad hoc </th> 
   <th colname="col4" class="entry"> Data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Alocação métrica </td> 
   <td colname="col2"> Mais recente </td> 
   <td colname="col3"> Mais recente </td> 
   <td colname="col4"> Mais recente </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valor expira após </td> 
   <td colname="col2"> Visita </td> 
   <td colname="col3"> Visita </td> 
   <td colname="col4"> Visita </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limites de valor </td> 
   <td colname="col2"> Nenhum limite (pode mudar em um lançamento futuro) </td> 
   <td colname="col3"> Nenhum limite (pode mudar em um lançamento futuro) </td> 
   <td colname="col4"> nenhum </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores especiais </td> 
   <td colname="col2"> <p>"Nenhum": totais de todo o site que não possuem um referenciador durante a visita. </p> </td> 
   <td colname="col3"> <p>"Nenhum": totais de todo o site que não possuem um referenciador durante a visita. </p> </td> 
   <td colname="col4"> <p> Vazio - equivalente a "Nenhum", representa os totais de todo o site que não possuem um referenciador durante a visita. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Notas {#section_B83A3571D64E4E7792712FAF740D7955}

* O referenciados, tipo de referenciador e domínio do mesmo estão definidos na primeira ocorrência de uma visita, ou durante uma visita quando o referenciador for externo (por exemplo, se um visitante sair do seu site, usar o mecanismo de busca e retornar ao site antes que a primeira visita expire). Esses valores estão definidos ao mesmo tempo e persistem em toda a visita.
* URLs internos estão filtrados. Apenas referenciadores que não correspondem aos Filtros internos do URL se encontram neste relatório.
* A métrica correspondente é chamada de Instância do referenciador na Ad Hoc Analysis.
* Valores Digitados/Marcados não são incluídos no Relatório de referenciadores. Isso significa que as Visitas de todo o site não correspondem às visitas neste relatório.

## Histórico de relatórios {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

<table id="table_9DFA79EC6A5A48648F2FB5418E1752DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Alterar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1/16/2014 </td> 
   <td colname="col2"> Data warehouse foi atualizado para corresponder à lógica usada e Reports &amp; Analytics de marketing. Até essa data, as palavras-chave de busca não persistiam durante toda a visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6/19/2012 </td> 
   <td colname="col2"> <p> Até julho de 2012, "Nenhum" incluía todos os tráfegos móveis, Digitado/Marcado, e visitas sem JavaScript. Após julho de 2012, "Nenhum" inclui apenas ocorrências sem nenhum JavaScript na primeira página da visita. </p> </td> 
  </tr> 
 </tbody> 
</table>

