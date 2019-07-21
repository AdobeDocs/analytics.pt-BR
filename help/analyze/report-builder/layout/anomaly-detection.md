---
description: A Detecção de anomalias utiliza um modelo estatístico para encontrar automaticamente tendências inesperadas em seus dados. O modelo analisa métricas e determina o intervalo de valores de limite inferior, limite superior e intervalo de valores. Quando ocorrer um pico ou uma queda inesperada, o sistema irá alertá-lo no relatório.
seo-description: A Detecção de anomalias utiliza um modelo estatístico para encontrar automaticamente tendências inesperadas em seus dados. O modelo analisa métricas e determina o intervalo de valores de limite inferior, limite superior e intervalo de valores. Quando ocorrer um pico ou uma queda inesperada, o sistema irá alertá-lo no relatório.
seo-title: Detecção de anomalias
solution: Analytics
title: Detecção de anomalias
topic: Construtor de relatórios
uuid: 02 da 21 b 4-3394-471 b -97 b 5-aa 1 bddf 1 f 445
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Detecção de anomalias{#anomaly-detection}

A Detecção de anomalias utiliza um modelo estatístico para encontrar automaticamente tendências inesperadas em seus dados. O modelo analisa métricas e determina o intervalo de valores de limite inferior, limite superior e intervalo de valores. Quando ocorrer um pico ou uma queda inesperada, o sistema irá alertá-lo no relatório.

Exemplos de anomalias que você pode investigar incluem:

* Quedas drásticas no valor médio de pedido
* Picos em pedidos com receita baixa
* Picos ou quedas em registros de avaliação
* Quedas em visualizações da página inicial
* Junções em eventos de buffer de vídeo
* Picos em taxas de vídeo baixas

>[!NOTE]
>
>A detecção de anomalias está disponível somente quando você seleciona a granularidade Dia.

<p class="head"> <b>Métricas para a detecção de anomalias</b> </p>

A detecção de anomalias adiciona novos valores de métrica a cada métrica selecionada, incluindo:

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Limite inferior </td> 
   <td colname="col2"> <p>Nível mais baixo do intervalo de previsão. Valores abaixo deste nível serão considerados anômalos. </p> <p>Representa uma confiança de 95% de que os valores estarão acima deste nível. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Esperado </td> 
   <td colname="col2"> <p>O valor previsto baseado na análise de dados. Este valor é ainda o ponto do meio entre os limites inferior e superior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite superior </td> 
   <td colname="col2"> <p>Nível mais alto do intervalo de previsão. Valores acima deste nível são considerados anômalos. </p> <p>Representa uma confiança de 95% de que os valores estarão abaixo deste nível. </p> </td> 
  </tr> 
 </tbody> 
</table>

O Construtor de relatórios aplica esses valores às métricas selecionadas. Por exemplo, se você selecionar uma métrica de Exibições de página e aplicar a detecção de anomalias, uma métrica de *`Page Views Lower Bound`* será utilizada.

**Como a detecção de anomalias é calculada**

A detecção de anomalias utiliza um período de treinamento para calcular, aprender e relatar os dados de previsão de intervalo por dia. Este período de treinamento é o período histórico que identifica aquilo que é normal e aquilo que é anômalo, e aplica o que aprendeu ao período do relatório. Em relatórios de marketing, estão disponíveis os períodos de treinamento de 30, 60 e 90 dias. O construtor de relatórios possui o período de 30 dias.

O período de treinamento não é necessariamente o mesmo que o período do relatório selecionado. Um gráfico do relatório exibe o intervalo de datas especificado no calendário.

Para calcular os dados, compara-se o total diário de cada métrica ao seu período de treinamento, usando cada um dos seguintes algoritmos:

* Holt Winters Multiplicative (Triple Exponential Smoothing)
* Holt Winters Additive (Triple Exponential Smoothing)
* Holts Trend Corrected (Double Exponential Smoothing)

Cada algoritmo é aplicado para determinar aquele com a menor Soma de erros ao quadrado (ou SSE em inglês). O Erro de porcentagem da média absoluta (MAPE, em inglês) e o Erro padrão atual são calculados para garantir que o modelo seja estatisticamente válido.

Esses algoritmos podem ser ampliados para fornecem previsões das métricas em períodos do futuro.

Como o período de treinamento pode variar por conta do início do período do relatório, é possível que haja diferenças entre os dados de uma mesma data relatados como parte de dois períodos diferentes.

Por exemplo, se você executar um relatório para o intervalo de datas de 1 a 14 de janeiro e logo depois um relatório para o intervalo de 7 a 21 de janeiro, você verá dados de previsão diferentes para uma mesma métrica entre os dias 7 a 14 de janeiro nos dois relatórios. Isso acontece devido à diferença entre os períodos de treinamento.

| Intervalo do relatório | Período de treinamento |
|--- |--- |
| 1 a 14 de janeiro | 27 de novembro - 31 de dezembro |
| 7 a 21 de janeiro | 4 de dezembro - 6 de janeiro |