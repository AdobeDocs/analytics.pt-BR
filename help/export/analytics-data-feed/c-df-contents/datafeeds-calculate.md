---
description: Descreve como calcular métricas comuns usando feeds de dados.
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
solution: Analytics
title: Calcular métricas
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Calcular métricas

Descreve como calcular métricas comuns usando feeds de dados.

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## Bots {#section_06753B95800F47668AAF52E7227F27C8}

Os bots são excluídos dos feeds de dados de acordo com as [regras de bot](https://marketing.adobe.com/resources/help/en_US/reference/bot_rules.html) definidas para o conjunto de relatórios.

## Filtragem de dados {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

Inclua linhas no intervalo da datas que deseja incluir filtrando o campo `date_time`. The `date_time` field is human readable (for example, `YYYY-MM-DD HH:MM:SS`) and is adjusted to the time zone of the report suite. For example, `date_time starts with "2013-12"` includes hits from December 2013.

## Sequência de evento {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. Recomendamos fazer todo o processamento no `post_event_list`, pois sua duplicata é removida e a lógica já é aplicada para remover eventos duplicados com a mesma ID (consulte [Serialização de eventos](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_event_serialization.html)).

Para a ID de evento de nomeação de mapeamento, consulte a pesquisa de evento fornecida com o feed de dados.

Para obter mais informações sobre eventos, consulte [Eventos](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html).

## Fórmulas para métricas comuns {#section_E26A01C234484857BF8C74443222AE41}

A tabela a seguir contém instruções para calcular várias métricas comuns.

<table id="table_814EA73C01EE4B2CA3CEB2839E19ADF9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Como calcular </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Exibições de página </td> 
   <td colname="col2"> <p> Page views can be calculated by counting when there is either a value in <code> post_pagename </code> or <code> post_page_url </code>. </p> 
    <p>É possível utilizar uma lógica semelhante para contar os links personalizados: </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code> post_page_event = 100 </code> para contar links personalizados. </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code> post_page_event = 101 </code> para contar os links de download. </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code> post_page_event = 102 </code> para contar os links de saída. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5, 8 e 9 são linhas de resumo carregadas por meio de fontes de dados. 7 representa os carregamentos de fonte de dados da ID de transação que não devem ser incluídos nas contagens de visita e de visitante. Consulte <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Pesquisa de fonte de hit </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">Combine <code> post_visid_high </code>, <code> post_visid_low </code>, <code> visit_num </code>e <code> visit_start_time_gmt </code>*. Conte o número exclusivo de combinações. </li> 
    </ol> <p>*Em raras ocasiões, as irregularidades da Internet, do sistema ou o uso das IDs do visitante personalizadas podem resultar em valores duplicados de <code> visit_num </code> para a mesma ID de visitante que não correspondem aos valores de <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html"  >visit </a>. To avoid resulting issues, also include <code> visit_start_time_gmt </code> when counting visits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5, 8 e 9 são linhas de resumo carregadas por meio de fontes de dados. 7 representa os carregamentos de fonte de dados da ID de transação que não devem ser incluídos nas contagens de visita e de visitante. Consulte <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Pesquisa de fonte de hit </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">Combine <code> post_visid_high </code> com <code> post_visid_low </code>. Conte o número exclusivo de combinações. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instâncias do evento </td> 
   <td colname="col2"> <p>When an event is set on a hit, <code> post_event_list </code> contains the event. The <code> post_event_list </code> is de-duplicated and is recommended to determine event instances. </p> <p>Por exemplo: </p> 
    <code>
      post_event_list = 1,200 
    </code> <p>Indicates an instance of <code> purchase </code> and <code> event1 </code>. </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">Exclude all rows with <code> hit_source = 5,8,9 </code>. São linhas de resumo carregadas por meio de fontes de dados. Consulte <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Pesquisa de fonte de hit </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">Count the number of times the event lookup value appears in <code> post_event_list </code>. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instâncias de eVar </td> 
   <td colname="col2"> <p>Quando uma eVar é definida em um hit, <code> event_list </code> contém uma instância dessa eVar. </p> <p>Por exemplo: </p> 
    <code>
      post_event_list&amp;nbsp;=&amp;nbsp;100,101,106 
    </code> <p>Indicates an instance of <code> eVar1 </code>, <code> eVar2 </code>, and <code> eVar7 </code>. Isso significa que o valor dessas três eVars foi definido no hit. </p> <p>Para calcular as instâncias das eVars, use a mesma lógica explicada em <i>Instâncias do evento</i> acima, mas conte o número de vezes em que a pesquisa de eVar aparece no <code> post_event_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo gasto </td> 
   <td colname="col2"> <p>Para calcular o tempo gasto, você deve agrupar os hits por visita e, em seguida, agrupá-los de acordo com o número do hit dentro da visita. </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">Group hits for a visit by concatenating <code> visid_high </code>, <code> visid_low </code>, and <code> visit_num </code>. </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">Order hits for each visit by <code> visit_page_num </code>. </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Using <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-page-event.md"  > page_event </a>, filter the types of hits you want. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">Encontre hits nos quais valor que você deseja para monitorar o tempo gasto já está definido. Por exemplo: 
      <code>
        hit&nbsp;1:&nbsp;post_prop1=red hit&nbsp;2:&nbsp;post_prop1=blue 
      </code> </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">Subtract the <code> post_cust_hit_time </code> for hit 1 from the <code> post_cust_hit_time </code> for hit 2 to determine the seconds between these two hits. The result is the time spent for <code> post_prop1=red </code>. Se o resultado for negativo, significa que o hit foi recebido fora do serviço e que o cálculo deve ser descartado. </li> 
    </ol> <p>Esta lógica também serve para calcular o tempo gasto para outros valores. When calculating time spent, Analytics calculates time spent based on the time the value was set in a <code> track </code> ( <code> page_event=0 </code>) or <code> trackLink </code> ( <code> page_event=10|11|12 </code>) call, to the time of the next page view ( <code> track </code> call). </p> <p>Ao relatar o tempo gasto para um determinado período, os Reports &amp; Analytics de marketing e a Ad Hoc Analysis avaliam hits externos ao período do relatório para determinar o tempo gasto com valores dentro do período de relatório, exceto quando a data de início e de término do período são determinadas mensalmente. Dada a complexidade desses cálculos, pode ser difícil igualar perfeitamente as métricas de tempo gasto. O data warehouse não avalia hits que ultrapassam o período de relatório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Receita, pedidos, unidades </td> 
   <td colname="col2"> <p>A conversão de moeda é aplicada ao <code> post_product_list </code> de acordo com as configurações do conjunto de relatórios. Portanto, é recomendado usar essa coluna. </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">Exclude all rows with <code> hit_source = 5,8,9 </code>. 5-9 representam as linhas de resumo carregadas por meio das fontes de dados. Consulte <a href="/help/export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md"  > Pesquisa de fonte de hit </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">Ignore purchase data for rows where <code> duplicate_purchase = 1 </code>. Esta sinalização indica que há duplicidade na compra (o que significa que um hit com o mesmo <code> purchaseID </code> já foi registrado). </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p>O <code> post_product_list </code> usa a mesma sintaxe como <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/c_products.html"  >s.products</a>. Portanto, é possível analisar essa sequência para calcular métricas. Por exemplo: </p> 
      <code>
        ;Cross Trainers;1;69.95,;Athletic Socks;10;29.99 
      </code> <p>Ao analisar a sequência, é possível determinar que 1 par de tênis de trilha foi comprado por US$ 69,95 e que a receita total da compra foi US$ 99,94. </p> </li> 
    </ol> <p>Observação: como o Analytics permite que eventos de moeda com a receita do produto sejam enviados na sequência de eventos, talvez seja necessário contabilizar a receita que não consta na sequência de produtos. Consulte <i>Eventos numéricos/de moeda</i> em <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html"  >s.events </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
