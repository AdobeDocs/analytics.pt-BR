---
description: As métricas são calculadas usando métodos padrão, de participação, recente e de alocação linear. Cada método calcula valores de forma diferente com base em fórmulas.
title: Cálculos de métricas
topic: Metrics
uuid: 2af58f1e-12c5-4828-ae39-c9aeaef6b705
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Cálculos de métricas

As métricas são calculadas usando métodos padrão, de participação, recente e de alocação linear. Cada método calcula valores de forma diferente com base em fórmulas.

<table id="table_6F81A12174D84124B7FD81FBBEDF18A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cálculo de métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Original </td> 
   <td colname="col2"> <p>É dado crédito total ao primeiro valor da variável associado ao evento bem-sucedido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recente </td> 
   <td colname="col2"> <p>É dado crédito total ao último valor da variável associado ao evento bem-sucedido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Linear </td> 
   <td colname="col2"> <p>Quando a alocação linear está selecionada, os eventos bem-sucedidos são divididos igualmente em todos os valores da variável vistos na visita. Em eventos numéricos e de moeda como  <span class="term"> Receita</span>, a quantidade monetária é dividida. Para eventos de contador como <span class="term"> Pedidos</span>, uma fração do evento é atribuída a cada valor variável na visita. Essas frações no relatório são somadas e arredondadas para o inteiro mais próximo no relatório. </p> <p>Por exemplo, em uma visita em que quatro páginas são visitadas antes de um evento bem-sucedido, cada página recebe crédito por 25% do evento. Se, na mesma visita, a <span class="varname">campanha</span> tivesse dois valores, cada valor de campanha receberia 50% do crédito do evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Participação </td> 
   <td colname="col2"> <p>Atribui crédito total a cada valor da variável que contribuiu para um evento bem-sucedido em uma visita. Este cálculo também pode se aplicar nas sessões de visitante, se você usar as métricas de participação de visita cruzada. </p> <p>Consulte <a href="/help/components/c-variables/c-metrics/metrics-participation.md"  > Participação</a> para obter mais informações. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplo - Cálculo de métrica {#section_4CE01DA35108418D9909823A7ECC4B45}

Suponha que seu site tenha uma pesquisa interna que é rastreada por meio de uma variável de conversão (eVar). O visitante realiza diversas pesquisas internas antes de realizar uma compra de US$100:

*`Pet`* > *`Feline`* > *`Cat`* > *`Kitten`* > compra de USD$100

Nos relatórios, a alocação de crédito acontece da seguinte maneira:

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valor da eVar </th> 
   <th colname="col2" class="entry"> Primeiro </th> 
   <th colname="col3" class="entry"> Último </th> 
   <th colname="col4" class="entry"> Linear </th> 
   <th colname="col5" class="entry"> Participação </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Animal de estimação </p> </td> 
   <td colname="col2"> <p>$100 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Felino </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gato </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filhote </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$100 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
 </tbody> 
</table>

