---
description: Classifica as páginas do site com base nas páginas que recebem mais tráfego. Se a sua dúvida de negócios lida com dados quantitativos para as páginas, você pode usar esse relatório para responder a essa dúvida, adicionando as métricas corretas.
title: Páginas
topic: Reports
uuid: 6435e262-e734-4c15-af5b-173799d5cc43
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Páginas

Classifica as páginas do site com base nas páginas que recebem mais tráfego. Se a sua dúvida de negócios lida com dados quantitativos para as páginas, você pode usar esse relatório para responder a essa dúvida, adicionando as métricas corretas.

## Alocação, expiração e valores especiais {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

Observe que em Reports &amp; Analytics, as métricas no Relatório de páginas usam uma alocação linear. Por exemplo, a receita é dividida entre todas as páginas visualizadas antes de um evento de compra. Isso pode causar certa confusão para algumas métricas que você planejava executar em apenas uma página, como a adição ao carrinho de compras.

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry">Relatórios &amp; <p>Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
   <th colname="col5" class="entry"> Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Alocação métrica </td> 
   <td colname="col2"> Linear </td> 
   <td colname="col3"> A alocação é específica de cada dimensão. O padrão é alocação de Último contato, mas a dimensão “'pagename” é uma exceção. Se você aplicar um evento personalizado a “pagename”, será uma alocação de Ocorrência exata. </td> 
   <td colname="col4"> <p>Valores definidos na mesma visualização de página </p> </td> 
   <td colname="col5"> <p>Valores definidos na mesma visualização de página </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valor expira após </td> 
   <td colname="col2"> Exibição da página </td> 
   <td colname="col3"> Exibição da página </td> 
   <td colname="col4"> Exibição da página </td> 
   <td colname="col5"> Exibição da página </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limites de valor </td> 
   <td colname="col2"> <p>Primeiros 500k exclusivos por mês + novos valores com tráfego </p> </td> 
   <td colname="col3"> <p>Primeiros 500k exclusivos por mês + novos valores com tráfego </p> </td> 
   <td colname="col4"> Nenhum </td> 
   <td colname="col5"> <p>Primeiros 500k exclusivos por mês + novos valores com tráfego </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores especiais </td> 
   <td colname="col2"> <p>(baixo tráfego) representa valores posteriores aos primeiros 500k, que não receberam tráfego suficiente para serem relatados. </p> </td> 
   <td colname="col3"> <p>(baixo tráfego) representa valores posteriores aos primeiros 500k, que não receberam tráfego suficiente para serem relatados. </p> </td> 
   <td colname="col4"> nenhum </td> 
   <td colname="col5"> <p>(baixo tráfego) representa valores posteriores aos primeiros 500k, que não receberam tráfego suficiente para serem relatados. </p> </td> 
  </tr> 
 </tbody> 
</table>

Em Reports &amp; Analytics, se você aplicar qualquer evento personalizado como métrica no relatório Páginas, a alocação linear se aplica.

Ou seja, mesmo se o evento foi enviado com uma chamada s.tl(), ele receberá uma alocação linear de qualquer chamada s.t() anterior. Exemplo:

| Nome da página | Page_event | Eventos |
|---|---|---|
| Página 1 | **s.t()** |  |
| Página 1 | s.tl() | Evento 1 |
| Página 1 | s.tl() | Evento 1 |
| Página 1 | s.tl() | Evento 1 |
| Página 2 | **s.t()** |  |
| Página 2 | **s.t()** |  |
| Página 2 | s.tl() | Evento 1 |

Nesse cenários, obteremos a seguinte alocação no relatório Páginas:

| Páginas | Pageviews | Evento 1 |
|---|---|---|
| Página 1 | 1 | 1+1+1+1/3 = 3,33 |
| Página 2 | 2 | 2/3 = 0,67 |

Mesmo se o evento for enviado em uma chamada s.tl, a página exibida antes do evento enviado (chamada s.t()) receberá crédito parcial.

## Notas {#section_47B0F4746D4847AC9E8697127063F4D0}

* O URL é usado se não existir um nome de página.
* Se existir uma ocorrência sem nome de página, URL de página ou lista de evento (sem evento comercial), a ocorrência é excluída.
* Detalhamentos em páginas exibem todas as páginas que tiveram um valor persistido.

