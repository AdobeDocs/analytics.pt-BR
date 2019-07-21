---
description: Selecionar o ícone de engrenagem ao lado de uma métrica permite especificar o tipo e o modelo de atribuição.
seo-description: Selecionar o ícone de engrenagem ao lado de uma métrica permite especificar o tipo e o modelo de atribuição.
seo-title: Atribuição e tipo de métrica
title: Atribuição e tipo de métrica
uuid: 64649698-df 2 a -42 c 3-bb 31-938 f 766 e 1 d 1 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Atribuição e tipo de métrica

Selecionar o ícone de engrenagem ao lado de uma métrica permite especificar o tipo e o modelo de atribuição.

* [Tipo de métrica](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [Modelo de atribuição de coluna](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [Como a alocação linear funciona (desde 19 de julho de 2018)](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## Tipo de métrica {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| Tipo de métrica | Definição |
|---|---|
| Padrão | These metrics are the same metrics used in standard [!DNL Analytics] reporting. Se uma fórmula consistir de uma única métrica padrão, ela exibirá dados idênticos à sua métrica não calculada equivalente. Métricas padrão são úteis ao criar métricas calculadas específicas para cada item de linha. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item. |
| Total | Use o total para informar o período de relatórios em cada item de linha. Se uma fórmula consistir em uma única métrica de total, ela exibirá o mesmo número total em cada item de linha. Métricas de total são úteis para a criação de métricas calculadas que comparam os dados totais do site. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item. |

## Modelo de atribuição de coluna {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>In July 2018, [!DNL Analytics] introduced [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), which revised the way allocation models in calculated metrics are evaluated. Como parte dessa alteração, as métricas calculadas que usam um modelo de alocação não padrão foram migradas para novos modelos de atribuição melhorados:
>
>* Para obter uma lista completa de modelos de atribuição não padrão e janelas de lookback com suporte, consulte a documentação do [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html).
>* Os modelos de alocação “Último contato do canal de marketing” e “Primeiro contato do canal de marketing” serão migrados para os novos modelos de atribuição “Último contato” e “Primeiro contato”, respectivamente (Observe que “Canais de marketing” não será descontinuado - apenas os dois modelos de alocação que aparecem nas métricas calculadas o serão).
>* Além disso, corrigiremos a maneira como a alocação linear é calculada. Para clientes que usam métricas calculadas com modelos de alocação “linear”, os relatórios podem ser levemente alterados para refletir o novo modelo de atribuição corrigido. This change to calculated metrics will be reflected in Analysis Workspace, [!UICONTROL Reports &amp; Analytics], the Reporting API, Report Builder, and Ad Hoc Analysis. Para obter mais informações, consulte [Como a alocação linear funciona (desde 19 de julho de 2018)](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1).
>



## Como a alocação linear funciona (desde 19 de julho de 2018) {#section_EDBB2E14A6C248C5A79C0913C02D7CA1}

Em julho de 2018, a Adobe alterou como a alocação linear é relatada para Métricas calculadas. This change impacts Analysis Workspace, Ad Hoc Analysis, [!UICONTROL Reports &amp; Analytics], Report Builder, Activity Map, and the Reporting APIs. A alteração afetará principalmente as eVars e outras dimensões que sejam persistentes. Note that these changes will only apply to calculated metrics and will not impact other reports using linear allocation (such as the Pages report in [!UICONTROL Reports &amp; Analytics]). Os outros relatórios que usam alocação linear continuarão a usar o método existente de alocação linear.

O seguinte exemplo ilustra como as métricas calculadas com alocação linear serão alteradas nos relatórios:

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Ocorrência 1 </th> 
   <th colname="col3" class="entry"> Ocorrência 2 </th> 
   <th colname="col4" class="entry"> Ocorrência 3 </th> 
   <th colname="col5" class="entry"> Ocorrência 4 </th> 
   <th colname="col6" class="entry"> Ocorrência 5 </th> 
   <th colname="col7" class="entry"> Ocorrência 6 </th> 
   <th colname="col8" class="entry"> Ocorrência 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dados de entrada </p> </td> 
   <td colname="col2"> PROMOÇÃO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMOÇÃO A </td> 
   <td colname="col5"> PROMOÇÃO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMOÇÃO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar de último contato </p> </td> 
   <td colname="col2"> PROMOÇÃO A </td> 
   <td colname="col3"> PROMOÇÃO A </td> 
   <td colname="col4"> PROMOÇÃO A </td> 
   <td colname="col5"> PROMOÇÃO B </td> 
   <td colname="col6"> PROMOÇÃO B </td> 
   <td colname="col7"> PROMOÇÃO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar de primeiro contato </p> </td> 
   <td colname="col2"> PROMOÇÃO A </td> 
   <td colname="col3"> PROMOÇÃO A </td> 
   <td colname="col4"> PROMOÇÃO A </td> 
   <td colname="col5"> PROMOÇÃO A </td> 
   <td colname="col6"> PROMOÇÃO A </td> 
   <td colname="col7"> PROMOÇÃO A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exemplo de propriedade </p> </td> 
   <td colname="col2"> PROMOÇÃO A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> PROMOÇÃO A </td> 
   <td colname="col5"> PROMOÇÃO B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> PROMOÇÃO C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

Neste exemplo, os valores A, B e C foram enviados para uma variável nas ocorrências 1, 3, 4 e 6 antes de uma compra de US$10 ser feita na ocorrência 7. Na segunda linha, esses valores persistem entre as ocorrências com base na visita do último contato. A terceira linha ilustra uma persistência na visita do primeiro contato. Por fim, a última linha ilustra como os dados seriam relatados para uma propriedade que não tenha persistência.

**Resumo de como a alocação linear funcionava antes de julho de 2018**

Antes de 19 de julho de 2018, a atribuição linear era calculada após a persistência do primeiro contato ou do último contato já ter ocorrido. Isso significava que para a eVar último contato acima, os US$10 seriam distribuídos da seguinte maneira: A = 10 * (3/6) = US$5, B = 10 * (2/6) = US$3,33, C = 10 * (1/6) = US$1,67.

Para a eVar primeiro contato acima, todos os US$10 seriam dados a A. Para a propriedade: A = 10 * (2/4) = US$5, B = 10 * (1/4) = US$2,50 e C = 10 * (1/4) = US$2,50. Para resumir a alocação linear como ela funcionava anteriormente:

| Valores | eVar de último contato atual | eVar de primeiro contato atual | Propriedade atual |
|---|---|---|---|
| PROMOÇÃO A | US$5,00 | US$10,00 | US$5,00 |
| PROMOÇÃO B | US$3,33 | $0 | US$2,50 |
| PROMOÇÃO C | US$1,67 | $0 | US$2,50 |
| Total | US$10,00 | US$10,00 | US$10,00 |

**Resumo de como a alocação linear funciona desde 19 de julho de 2018**

Em 19 de julho de 2018, corrigimos este comportamento nas métricas calculadas. Instead of using the persisted values based on last touch or first touch, [!DNL Analytics] now uses only the values that were passed in (the first row of the top table). Sendo assim, as configurações de alocação de dimensão não afetam mais a maneira como a alocação linear é calculada (isso significa que propriedades e eVars serão tratadas da mesma maneira) e os resultados reflete o que foi originalmente passado em vez dos valores do primeiro ou do último contato que possam ter persistido. Então, em todos os três casos, A = 10 * (2/4) = US$5, B = 10 * (1/4) = US$2,50 e C = 10 * (1/4) = US$2,50.

| Valores | Nova eVar de último contato | Nova eVar de primeiro contato | Nova propriedade |
|---|---|---|---|
| PROMOÇÃO A | US$5,00 | US$5,00 | US$5,00 |
| PROMOÇÃO B | US$2,50 | US$2,50 | US$2,50 |
| PROMOÇÃO C | US$2,50 | US$2,50 | US$2,50 |
| Total | US$10,00 | US$10,00 | US$10,00 |

<!-- 

<p>Additionally, as part of this change, [!DNL Analytics] is <b>changing how multiple sequential successes</b> are treated. In the following example, 7 hits occurred in the same visit with two orders, one $10 order on hit 4, and one $5 order on hit 7: </p> 
<table id="table_4647AA466D1447F6961DDC10468FCCE1"> 
 <tgroup cols="8">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="1.04*" />
  <colspec colnum="3" colname="col3" colwidth="1.02*" />
  <colspec colnum="4" colname="col4" colwidth="1.02*" />
  <colspec colnum="5" colname="col5" colwidth="1.03*" />
  <colspec colnum="6" colname="col6" colwidth="1.02*" />
  <colspec colnum="7" colname="col7" colwidth="1.02*" />
  <colspec colnum="8" colname="col8" colwidth="1.03*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> </th> 
    <th colname="col2" class="entry"> Hit 1 </th> 
    <th colname="col3" class="entry"> Hit 2 </th> 
    <th colname="col4" class="entry"> Hit 3 </th> 
    <th colname="col5" class="entry"> Hit 4 </th> 
    <th colname="col6" class="entry"> Hit 5 </th> 
    <th colname="col7" class="entry"> Hit 6 </th> 
    <th colname="col8" class="entry"> Hit 7 </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Data Sent In </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Last Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO B </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>First Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO A </td> 
    <td colname="col7"> PROMO A </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Example prop </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p>Currently (<b>prior to July 19, 2018</b>), linear attribution would carry forward past the initial conversion and persist into the second conversion </p> 
<ul id="ul_FD09813B59F04FF2A96A70BBE0A8F349"> 
 <li id="li_2EC965DDAE334C1795530F7C6F1674C5">In our first-touch eVar example, the total revenue for each promotion would be calculated using the promos prior to conversion on hit 4 for revenue on hit 4, but all promos for the conversion on hit 7. </li> 
 <li id="li_687C03C4B0A941AA800084F324A95FD6">In our last-touch eVar example, this would be: A = (2/3) * 10 + (2/5) * 5 = $8.66, B = (1/3) * 10 + (2/5) * 5 = $5.33, C = (1/5) * 5 = $1.00. In our FT eVar example: A = (3/3) * 10 + (5/5) * 5 = $15.00, and for the prop: A = (1/2) * 10 + (1/3) * 5 = $6.66, B = (1/2) * 10 + (1/3) * 5 = $6.66, and C = (1/3) * 5 = $1.66. </li> 
</ul> 
<p>Resulting in a distribution as follows: </p> 
<table id="table_6A066E602BF641B0BD4B175EE9753C6E"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> Current Last Touch eVar </th> 
    <th colname="col3" class="entry"> Current First Touch eVar </th> 
    <th colname="col4" class="entry"> Current Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $8.66 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.33 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $1.00 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $1.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p><b>After July 19, 2018</b>, [!DNL Analytics] will treat each sequence of conversions independently, meaning linear attribution will no longer carry forward from one conversion to another. In the previous example, attribution will always be treated the same way (regardless of the eVar allocation settings as stated above) and will be calculated as follows: A = (1/2) * 10 = $5, B = (1/2) * 10 = $5, and C = (1/1) * 5 = $5. To summarize: </p> 
<table id="table_2D39CCD158BF488EA404324DF50B9579"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> New Last Touch eVar </th> 
    <th colname="col3" class="entry"> New First Touch eVar </th> 
    <th colname="col4" class="entry"> New Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

