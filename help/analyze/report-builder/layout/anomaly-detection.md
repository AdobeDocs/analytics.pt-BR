---
description: A Detecção de anomalias utiliza um modelo estatístico para encontrar automaticamente tendências inesperadas em seus dados. O modelo analisa métricas e determina o intervalo de valores de limite inferior, limite superior e intervalo de valores. Quando ocorre um pico ou uma queda inesperada, o sistema alerta você no relatório.
title: Detecção de anomalias
topic: Report builder
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Detecção de anomalias {#anomaly-detection}

A Detecção de anomalias utiliza um modelo estatístico para encontrar automaticamente tendências inesperadas em seus dados. O modelo analisa métricas e determina o intervalo de valores de limite inferior, limite superior e intervalo de valores. Quando ocorre um pico ou uma queda inesperada, o sistema alerta você no relatório.

Exemplos de anomalias que você pode investigar incluem:

* Quedas drásticas no valor médio da ordem
* Picos em pedidos com baixa receita
* Picos ou quedas em registros de avaliação
* Quedas em visualizações de landing page
* Especificações em eventos de buffer de vídeo
* Picos em taxas de bits de vídeo baixas

>[!NOTE] A detecção de anomalias só estará disponível depois da seleção da granularidade do dia.

<p class="head"> <b>Métricas de detecção de anomalias</b> </p>

A detecção de anomalias adiciona novos valores de métrica para cada métrica selecionada, incluindo:

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
   <td colname="col2"> <p>Nível mais baixo do intervalo de previsão. Valores abaixo desse nível são considerados anômalos. </p> <p>Representa uma confiança de 95% de que os valores estarão acima desse nível. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Esperado </td> 
   <td colname="col2"> <p>O valor previsto com base na análise de dados. Esse valor também é o ponto médio entre os limites superior e inferior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite superior </td> 
   <td colname="col2"> <p>Nível superior do intervalo de previsão. Valores acima desse nível são considerados anômalos. </p> <p>Representa uma confiança de 95% de que os valores estarão abaixo desse nível. </p> </td> 
  </tr> 
 </tbody> 
</table>

O Report Builder aplica esses valores às métricas selecionadas. Por exemplo, se você selecionar uma métrica de Exibições de página e aplicar a detecção de anomalias, uma métrica de *`Page Views Lower Bound`* será utilizada.

**Como a detecção de anomalias é calculada**

A detecção de anomalias usa um período de treinamento para calcular, aprender e relatar dados de previsão de intervalo por dia. O período de treinamento é o período histórico que identifica o que é normal vs. anômalo e aplica o que é aprendido ao período do relatórios. Nos relatórios de marketing, os períodos de treinamento de 30, 60 e 90 estão disponíveis. O Report Builder possui o período de 30 dias.

O período de treinamento não é necessariamente o mesmo que o período de relatórios selecionado. Um gráfico de relatório exibe o período de intervalo de datas especificado no calendário.

Para calcular os dados, o total diário de cada métrica é comparado ao período de treinamento usando cada um dos seguintes algoritmos:

* Multiplicativo de Holt Winters (Suavização exponencial tripla)
* Aditivo de Holt Winters (Suavização exponencial tripla)
* Tendência de Holts corrigida (Suavização exponencial dupla)

Cada algoritmo é aplicado para determinar aquele com a menor Soma de erros ao quadrado (ou SSE em inglês). O Erro de porcentagem média absoluta (MAPE) e o Erro padrão atual são calculados para garantir que o modelo seja estatisticamente válido.

Esses algoritmos podem ser estendidos para fornecer previsões de métricas em períodos futuros.

Como o período de treinamento varia com base no start do período do relatórios, você pode observar diferenças nos dados reportados para a mesma data como parte de dois períodos diferentes.

Por exemplo, se você executar um relatório para 1 a 14 de janeiro e, em seguida, executar um relatório para 7 a 21 de janeiro, poderá ver dados de previsão diferentes para a mesma métrica entre 7 e 14 de janeiro nos dois relatórios diferentes. Isso resulta da diferença entre os períodos de treinamento.

| Intervalo de Relatórios | Período de treinamento |
|--- |--- |
| 1 a 14 de janeiro | 27 de novembro - 31 de dezembro |
| 7 a 21 de janeiro | 4 de dezembro - 6 de janeiro |
