---
description: Mostra o número de visitantes únicos que acessaram site. Cada visitante é contado uma vez, independentemente de quantas vezes a pessoa visita site.
title: Visitantes únicos
topic: Reports
uuid: e70e1a14-b3b9-4d1a-a8a5-a247a443c752
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visitantes únicos

Mostra o número de visitantes únicos que acessaram site. Cada visitante é contado uma vez, independentemente de quantas vezes a pessoa visita site.

**Dados da Amostra**

Consulte a tabela a seguir para obter exemplos nesta página. O mesmo visitante é representado aqui:

<table id="table_4F54873A4ED8451494E466C2BDB15B00"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> 01/01/2017 </th> 
   <th colname="col3" class="entry"> 01/01/2017 </th> 
   <th colname="col4" class="entry"> 02/01/2017 </th> 
   <th colname="col5" class="entry"> 02/01/2017 </th> 
   <th colname="col6" class="entry"> 02/01/2017 </th> 
   <th colname="col7" class="entry"> 03/01/2017 </th> 
   <th colname="col8" class="entry"> 04/01/2017 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Página </p> </td> 
   <td colname="col2"> <p>A </p> </td> 
   <td colname="col3"> <p>C </p> </td> 
   <td colname="col4"> <p>A </p> </td> 
   <td colname="col5"> <p>B </p> </td> 
   <td colname="col6"> <p>C </p> </td> 
   <td colname="col7"> <p>D </p> </td> 
   <td colname="col8"> <p>E </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar </p> </td> 
   <td colname="col2"> <p>T, U </p> </td> 
   <td colname="col3"> <p>V </p> </td> 
   <td colname="col4"> <p>W </p> </td> 
   <td colname="col5"> <p> </p> </td> 
   <td colname="col6"> <p>X, Y </p> </td> 
   <td colname="col7"> <p>Z </p> </td> 
   <td colname="col8"> <p>Z </p> </td> 
  </tr> 
 </tbody> 
</table>

## Relatório de Visitantes únicos - Métrica de tendência {#section_372C08A881D34BBF811C1DE0A1460617}

Os relatórios [!UICONTROL Visitantes únicos] se comportam de forma semelhante na Ad Hoc Analysis. Para cada ocorrência de visita, o visitante é contado nessa ocorrência. Cada página recebe crédito por ter o visitante nessa página.

<table id="table_7D9119045E8243698B6BB2E8C93F6B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página </th> 
   <th colname="col2" class="entry"> Visitantes únicos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

Além disso, cada data recebe crédito por ter esse visitante naquela data.

<table id="table_E0D06D9434444947BDA818F61A580B65"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitantes únicos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 1 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 3 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 4 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL Relatório de Visitantes únicos]dividido por *`Page`*.**

Você pode selecionar uma página para o [!UICONTROL Relatório de Visitantes únicos]. No relatório a seguir, o visitante visita a página A nessas datas:

<table id="table_2ABA17B19E0D4F92AAB003BE784DA9E0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitantes únicos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 1 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 3 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 4 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Visitantes únicos Baseados em Período (Tendência) {#section_B3502EBF1ACB487AA8E0EFBA9A0561FD}

Você pode executar [!UICONTROL Relatórios de Visitantes únicos] por hora, por semana, por mês, por trimestre e por ano (tendência).

Os visitantes únicos baseados em período são contados somente na primeira visita durante o período especificado. Por exemplo, os Visitantes únicos por hora são contados pela primeira visita durante a hora especificada. Os Visitantes únicos por dia são contados pela primeira visita no dia especificado.

<table id="table_FF14F05CDFDA4F2E92A62D9D751A1CAA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitantes únicos semanais </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 1 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 2 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 3 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 4 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

O relatório a seguir exibiria os Visitantes únicos por dia.

<table id="table_4E44BC4722064501A5B648BE80ED8E60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitantes únicos por dia </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 1 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 3 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 4 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>4 </p> </td> 
  </tr> 
 </tbody> 
</table>

Os totais da métrica podem alterar com base no intervalo de datas do relatório. Os relatórios de marketing começam a contar os Visitantes únicos com base no tempo a partir do início do intervalo de datas. Por exemplo, se o intervalo de datas for de 2 de janeiro a 3 de janeiro, os resultados seguintes mostrariam os Visitantes únicos semanais:

<table id="table_B695708BB22949E7BA293FE492D2EEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitantes únicos semanais </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 3 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

**Segmentação**

Você pode utilizar segmentação para alterar o intervalo de datas pra incluir datas posteriores em vez de datas anteriores. Por exemplo, suponhamos que o intervalo de datas seja de 2 de janeiro a 3 de janeiro (conforme mostrado na tabela anterior). Se você aplicar um segmento onde Página = C, 2 de janeiro passaria para o segmento, e a primeira ocorrência do Visitante Único por semana seria no dia 3 de janeiro. Se, ao invés disso, você aplicar um segmento onde Página = D, então tanto o dia 2 de janeiro quanto o dia 3 de janeiro serão excluídos. Nenhum resultado seria mostrado para o Visitante Único por semana e seria excluído do total.

**Relatórios de Visitantes únicos Baseados em Período**

Estes relatórios utilizam uma página particular, prop e atributos (exemplo: onde Página = A).

Suponhamos que você vise um [!UICONTROL Relatório de Páginas] com uma métrica de Visitante Único baseado em período. Se houver um detalhamento ou uma variável selecionada para os relatórios de Visitantes únicos com base no período, os relatórios de marketing contarão todas as instâncias do visitante e do par de atributo. Para a primeira ocorrência do visitante, este processamento não é diferente dos exemplos anteriores. Para ocorrências subsequentes, estes relatórios incluem ocorrências que os relatórios acima não incluem, se a página for diferente.

Para Visitantes únicos por semana onde a Página = A, os relatórios de marketing excluem o dia 2 de janeiro dos totais. Essa exclusão ocorre, pois os relatórios de marketing já contaram o Visitante Único por semana no dia 1 de janeiro. Eis um relatório de visitantes únicos onde Página = A:

<table id="table_9C5E00029C7340B28D76696E84F66511"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitantes únicos semanais </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 1 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 2 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 3 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 4 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

Para visitantes únicos por semana onde a Página = B, a única data em que ocorre é 2 de janeiro, conforme mostrado a seguir:

<table id="table_262150BECCB74120B58F506F4BC6F629"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Visitas - Visitantes únicos semanais </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 1 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 3 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Janeiro de 4 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas de visitante único baseadas em período em relatórios de tendências {#section_90B784F4E49F4930B3F0923B95958BA2}

Você pode adicionar métricas de visitantes únicos baseadas em período a relatórios de tendências, como uma métrica de Visitantes únicos semanais em um [!UICONTROL Relatório de Páginas].

<table id="table_8651A42696B0404CAEAE0FC5522CC1C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página </th> 
   <th colname="col02" class="entry"> Data da Visita </th> 
   <th colname="col2" class="entry"> Visitas - Visitante Único por semana </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col02"> <p>Janeiro de 1 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col02"> <p>Janeiro de 2 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col02"> <p>Janeiro de 3 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col02"> <p>Janeiro de 4 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E </p> </td> 
   <td colname="col02"> <p>Janeiro de 5 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col02"> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

Uma métrica de Visitantes únicos por dia em um [!UICONTROL Relatório de Páginas] mostraria:

<table id="table_04C7C305C2B945D6A79A6B80F48A4BF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página </th> 
   <th colname="col02" class="entry"> Data da Visita </th> 
   <th colname="col2" class="entry"> Visitas </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col02"> <p>Janeiro de 1 </p> </td> 
   <td colname="col2"> <p>2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col02"> <p>Janeiro de 2 </p> </td> 
   <td colname="col2"> <p>2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col02"> <p>Janeiro de 3 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col02"> <p>Janeiro de 4 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col02"> <p> </p> </td> 
   <td colname="col2"> <p>4 Visitantes únicos por dia </p> </td> 
  </tr> 
 </tbody> 
</table>

Para dividir um atributo por outro (como *`page`* da *`eVar`*), o Analytics aloca um Visitante Único com base em período para cada instância única do período e da página (ou do atributo sendo correlacionado).

Se você dividir a Página A por eVars T, U, o dia 2 de janeiro será excluído, pois a página A foi visualizada no dia 1 de janeiro. Os resultados a seguir mostrariam os Visitantes únicos semanais:

<table id="table_328A6F2E920A44B3B55A6E6A630F6DBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar </th> 
   <th colname="col2" class="entry"> Visitantes únicos semanais </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>T </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>U </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cookies persistentes {#section_81E139F08AEB4E30A06472856975EA1E}

Os cookies persistentes continuam no computador do visitante entre visitas para que a Adobe possa identificar os visitantes de visitas subsequentes. Para visualizar o percentual de usuários que aceitam ou não os cookies persistentes, selecione **[!UICONTROL Filtro]** &gt; **[!UICONTROL Cookies persistentes]**.

O gráfico e a visualização de detalhes mostram visitantes de cookie persistente e não persistente. Frequentemente, a quantidade de visitantes de cookies não persistentes é insignificante.
