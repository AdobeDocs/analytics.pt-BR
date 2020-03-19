---
description: Um relatório de tendências que exibe o número de vezes em que as páginas do site foram visualizadas durante o intervalo selecionado (hora, dia, semana, mês, trimestre ou ano). Este relatório permite que você acompanhe as visualizações de páginas para cada página no site, bem como um agregado de exibições de página do site inteiro.
title: Exibições de página
topic: Reports
uuid: c78260c6-9ad4-4b85-84fd-763627392e44
translation-type: tm+mt
source-git-commit: 707b61d853a8ec68b3f77a35a1aa5f0c7dd8a1fd

---


# Exibições de página

Um relatório de tendências que exibe o número de vezes em que as páginas do site foram visualizadas durante o intervalo selecionado (hora, dia, semana, mês, trimestre ou ano). Este relatório permite que você acompanhe as visualizações de páginas para cada página no site, bem como um agregado de exibições de página do site inteiro.

Uma [Exibição de página](/help/components/c-variables/c-metrics/metrics-page-view.md) é uma solicitação de um documento de página inteira, em vez de um elemento de uma página, como uma imagem ou vídeo. Por exemplo, se um único visitante visualiza 15 páginas durante uma visita, isso é contado como 15 exibições de página. Se um usuário visita a mesma página três vezes durante uma visita, três visualizações de páginas são contadas.

## Propriedades do relatório

* This report references the number of times the [`t()`](/help/implement/vars/functions/t-method.md) method is called on your site.
* As chamadas de rastreamento de link que usam o [`tl()`](/help/implement/vars/functions/tl-method.md) método não são contadas neste relatório.
* Por que as solicitações de imagens são enviadas quando o usuário atualiza a página ou clica no botão voltar, este relatório também inclui essas ações.
* Os detalhamentos por hora são baseados na zona de tempo do conjunto de relatórios.
* Este relatório não contém itens de linha. Como tal, o relatório pode ser visualizado somente no formato geral.
* A granularidade de hora, dia, semana, mês, trimestre e ano pode ser aplicada. Essa granularidade está disponível dependendo do intervalo da data do relatório.

## Informações específicas do produto

<table id="table_61F964F47D1D43508B271999F495F7F9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Conteúdo do site</span> &gt; <span class="uicontrol">Visualizações da página</span> </p> <p>Este relatório pode usar segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DB66B8F9F6BF473A83EC7668F59776D0"> 
     <li id="li_D1CB486058F040859560D5BFDF3972EE"> Analise cada item neste relatório por todos os relatórios e variáveis, permitindo que você veja os detalhamentos por qualquer granularidade. </li> 
     <li id="li_BAADA9ADDD6F47B08D129FD30CD8EF2E">Você pode usar todas as métricas de conversão e tráfego neste relatório, assim como uma alocação diferente para todas as métricas de conversão. </li> 
     <li id="li_3696CA6E0BD54305B3609CCC80F851BA">Este relatório pode usar múltiplos segmentos altamente avançados. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

