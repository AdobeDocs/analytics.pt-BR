---
description: Exibe em média em que ponto da visita cada valor foi disparado. Esta métrica é importante para determinar em que ponto de uma visita o público-alvo alcança uma página ou valor de prop determinado. Profundidade média da página está disponível em qualquer variável com definição de caminho ativada.
title: Profundidade média da página
topic: Metrics
uuid: 4d8a3a3c-c698-4210-8dd8-a02a1638483c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Profundidade média da página

Exibe em média em que ponto da visita cada valor foi disparado. Esta métrica é importante para determinar em que ponto de uma visita o público-alvo alcança uma página ou valor de prop determinado. Profundidade média da página está disponível em qualquer variável com definição de caminho ativada.

Por exemplo: se uma visita contém o seguinte caminho: Página A &gt; Página B &gt; Página C &gt; Página D &gt; Página E &gt; Página F, a profundidade é um índice de onde está a página. Por exemplo: "Página A" tem uma profundidade de 0, enquanto a "Página F." tem uma profundidade de cinco. A média é baseada em uma combinação de todas as visitas. Uma profundidade da página com um valor de menos que um (como 0,9) é o valor médio de todas as páginas visitas antes da página em questão.

A [!UICONTROL profundidade da página] ajuda você a entender onde uma determinada página normalmente resulta em um caminho de usuário, independentemente das páginas anteriores ou posteriores neste caminho. Como tal, ajuda a fornecer insight em como a página se encaixa no quadro geral da experiência do usuário do site. Este insight pode ser melhor visto em um relatório de [!UICONTROL Páginas].

<table id="table_E92B185A487C40E28C70EA30EDF73A40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Usos </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tráfego </td> 
   <td colname="col2"> <p>O cálculo de eventos de páginas e páginas visualizadas dividido por visitas, mostrando o número de clique médio de uma página. Considere o mesmo caminho de visita: </p> <p>A &gt; B &gt; B &gt; C &gt; D &gt; B </p> <p>O número de cliques é calculado para cada página e cada evento, incluindo recargas nas quais a opção "Contar instâncias repetidas" está ativada (isto é, por padrão, uma Ad Hoc Analysis, e estará sempre ativada em Marketing Reports and Analytics). Nesta visita, a página A recebeu um número de cliques de 0. Para a página B, o número de clique seria 1, 2 e 5. O cálculo para a média seria [(1+2+5) / 3] para uma Profundidade de página média de 2.67 para a página B. </p> <p>Quando a opção "Contar instâncias repetidas" estiver ativada, a página B receberá 1 e 4. A segunda não será levada em conta. O cálculo seria [(1+4) / 2 = 2.5]. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversão </td> 
   <td colname="col2"> N/D </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Relatório de Profundidade da página](/help/components/c-variables/dimensionslist/reports-page-depth.md)

