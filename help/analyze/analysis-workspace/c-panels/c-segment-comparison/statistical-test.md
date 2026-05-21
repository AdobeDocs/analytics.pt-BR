---
description: Saiba como os testes estatísticos são usados na comparação entre segmentos.
keywords: Analysis Workspace;Segment IQ
title: Testes Estatísticos Usados Na Comparação De Segmentos
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
TQID: https://experienceleague.adobe.com/49kZ6LC9OMizQvqxE2PCq1LtqhUHtf5iKQUgpgqSmmE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 9%

---

# Testes estatísticos usados na comparação entre segmentos

Cada uma das principais tabelas de comparação mostra uma pontuação de diferenças. Essa pontuação é calculada por vários testes estatísticos, dependendo da comparação que está sendo feita. No entanto, independentemente do teste usado, a pontuação de diferença é mostrada como um valor entre 0 e 1.

Uma pontuação de 0 significa que não há diferença entre os dois segmentos e uma pontuação de 1 significa que houve uma diferença muito grande entre os dois segmentos. Há dois tipos de testes estatísticos empregados para gerar essas pontuações de diferença:

* Para a tabela **[!UICONTROL Métricas principais]**, é usado um teste U de Mann-Whitney,
* Para a tabela **[!UICONTROL Principais Itens da Dimension]** e **[!UICONTROL Principais Segmentos]**, uma comparação de diferença de risco é usada.

## Pontuação de diferenças das principais métricas

Na tabela Métricas principais, a Ferramenta de comparação de segmentos usa dois exemplos de Teste de Mann-Whitney U. Este teste é um teste de igualdade não paramétrico usado para comparar as distribuições de probabilidade unidimensionais de cada métrica para cada segmento considerado. A pontuação de diferenças na tabela de métricas é uma combinação do valor p da estatística U calculada (que representa a diferença estocasticamente distinta entre os dois segmentos em uma métrica específica) e a magnitude relativa da diferença observada. Uma pontuação de diferenças grande (próxima a 1) significa que a métrica específica tem uma grande diferença relativa, bem como uma alta confiança estatística de que os segmentos são diferentes.

## Pontuação de diferenças nos principais itens de dimensão e nas principais diferenças entre segmentos

Para calcular a pontuação de diferenças nas tabelas Principais Itens Dimension e Principais Diferenças entre Segmentos, um algoritmo de diferenciação de risco relativo é usado (semelhante ao índice de risco, embora usando uma diferença em vez de um índice). Uma diferença de risco é calculada subtraindo-se as incidências cumulativas de um item de dimensão (ou sobreposição com um segmento da tabela de segmentos) de um segmento selecionado do outro. Uma pontuação de diferença alta (próxima a 1) significa que um determinado item de dimensão ou segmento terciário era muito proeminente em um dos segmentos selecionados e não no outro.

>[!NOTE]
>
>Nos três gráficos, a estatística de diferença é baseada em uma amostra adequada de visitantes para fazer com que o processo seja executado da maneira mais rápida possível e se mantenha estatisticamente preciso. Embora a pontuação de diferenças se baseie em uma amostra, os resultados apresentados na tabela não são amostrados. Para garantir significância estatística, cada teste estatístico depende de um algoritmo de alocação dinâmica de modo que o segmento menor contenha um tamanho de amostra que forneça menos de 3% de margem de erro. Se um segmento contiver muito poucos visitantes (menos de 1.000), todos os dados disponíveis serão usados em vez da amostra para calcular a pontuação de diferenças.
