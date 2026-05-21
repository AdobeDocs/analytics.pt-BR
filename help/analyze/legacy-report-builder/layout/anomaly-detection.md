---
description: Saiba mais sobre a Detecção de anomalias e como ela é calculada.
title: Como a Detecção de anomalias é usada para encontrar tendências automaticamente
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: User, Admin
exl-id: 6e3881c8-3e1c-4df8-ba38-e8bc84cfc3d4
TQID: https://experienceleague.adobe.com/P2dvU8YgWcjCZ6h4oTxK-2-z1X3-wl-oMp70UIJGeXo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: c67272a6-888e-425e-9e97-a87304637eed
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 511
ht-degree: 26%

---

# Detecção de anomalias{#anomaly-detection}

{{legacy-arb}}

A Detecção de anomalias utiliza um modelo estatístico para encontrar automaticamente tendências inesperadas em seus dados. O modelo analisa métricas e determina um limite inferior, um limite superior e o intervalo esperado de valores. Quando ocorrer um pico ou uma queda inesperada, o sistema irá alertá-lo no relatório.

Exemplos de anomalias que você pode investigar incluem:

* Quedas drásticas no valor diário de pedidos
* Picos em pedidos com baixa receita
* Picos ou quedas em registros de avaliação
* Quedas nas exibições da página de destino
* Especiarias em eventos de buffer de vídeo
* Picos em taxas de bits de vídeo baixas

>[!NOTE]
>
>A detecção de anomalias só estará disponível depois da seleção da granularidade do dia.

<p class="head"> <b>Métricas de Detecção de Anomalias</b> </p>

A Detecção de anomalias adiciona novos valores de métrica para cada métrica selecionada, incluindo:

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
   <td colname="col2"> <p>Nível inferior do intervalo de previsão. Valores abaixo desse nível são considerados anômalos. </p> <p>Representa uma confiança de 95% de que os valores estarão acima desse nível. </p> </td> 
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

O Report Builder aplica esses valores às métricas selecionadas. Por exemplo, se você selecionar uma métrica de Exibições de página e aplicar a detecção de anomalias, será usada uma métrica *`Page Views Lower Bound`*.

**Como A Detecção De Anomalias É Calculada**

A Detecção de anomalias usa um período de treinamento para calcular, aprender e relatar dados de intervalo de previsão por dia. O período de treinamento é o período histórico que identifica o que é normal vs. anômalo e aplica o que é aprendido ao período dos relatórios. Nos relatórios de marketing, os períodos de treinamento de 30, 60 e 90 estão disponíveis. No Report Builder, 30 dias estão disponíveis.

O período de treinamento não é necessariamente o mesmo que o período de relatório selecionado. Um gráfico de relatórios exibe o intervalo de datas especificado no calendário.

Para calcular os dados, o total diário de cada métrica é comparado ao período de treinamento usando cada um dos seguintes algoritmos:

* Multiplicativo de Holt Winters (Suavização exponencial tripla)
* Aditivo de Holt Winters (Suavização exponencial tripla)
* Tendência de Holts corrigida (Suavização exponencial dupla)

Cada algoritmo é aplicado para determinar aquele com a menor Soma de erros ao quadrado (ou SSE em inglês). O erro percentual absoluto médio (MAPE) e o erro padrão atual são calculados para garantir que o modelo seja estatisticamente válido.

Esses algoritmos podem ser estendidos para fornecer previsões preditivas de métricas em períodos futuros.

Como o período de treinamento varia com base no início do período dos relatórios, você pode ver diferenças nos dados relatados para a mesma data como parte de dois períodos diferentes.

Por exemplo, se você executar um relatório para 1-14 de janeiro e, em seguida, executar um relatório para 21-7 de janeiro, poderá ver dados de previsão diferentes para a mesma métrica entre 7-14 de janeiro nos dois relatórios diferentes. Isso é resultado da diferença nos períodos de treinamento.

| Intervalo de relatório | Período de treinamento |
|--- |--- |
| 1º a 14 de janeiro | 27 de novembro - 31 de dezembro |
| 7-21 de janeiro | 4 de dezembro - 6 de janeiro |
