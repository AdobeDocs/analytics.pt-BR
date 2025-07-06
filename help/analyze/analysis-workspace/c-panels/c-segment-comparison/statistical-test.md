---
description: Saiba como os testes estatísticos são usados na comparação entre segmentos.
keywords: Analysis Workspace;Segment IQ
title: Testes Estatísticos Usados Na Comparação De Segmentos
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 43%

---

# Testes estatísticos usados na comparação entre segmentos

Cada uma das principais tabelas de comparação mostra uma pontuação de diferenças. Essa pontuação é calculada por vários testes estatísticos, dependendo da comparação que está sendo feita. No entanto, independentemente do teste usado, a pontuação de diferença é mostrada como um valor entre 0 e 1.

Uma pontuação de 0 significa que não há diferença entre os dois segmentos e uma pontuação de 1 significa que houve uma diferença muito grande entre os dois segmentos. Há dois tipos de testes estatísticos empregados para gerar essas pontuações de diferença:

* Para a tabela **[!UICONTROL Métricas principais]**, é usado um teste U de Mann-Whitney,
* Para a tabela **[!UICONTROL Principais Itens da Dimension]** e **[!UICONTROL Principais Segmentos]**, uma comparação de diferença de risco é usada.

## Pontuação de diferenças das principais métricas

Na tabela Métricas principais, a Ferramenta de comparação de segmentos usa dois exemplos de Teste de Mann-Whitney U. Este teste é um teste de igualdade não paramétrico usado para comparar as distribuições de probabilidade unidimensionais de cada métrica para cada segmento considerado. A pontuação de diferença no gráfico de métricas é uma combinação do valor p da estatística U computada (que representa a maneira diferente que os dois segmentos são distribuídos em uma determinada métrica) e a magnitude relativa da diferença observada. Uma pontuação de diferenças grande (próxima a 1) significa que a métrica específica tem uma grande diferença relativa, bem como uma alta confiança estatística de que os segmentos são diferentes.

## Pontuação de diferenças nos principais itens de dimensão e nas principais diferenças entre segmentos

Para computar a pontuação de diferença nos gráficos Principais itens de dimensão e Principais diferenças entre segmentos, é usado um algoritmo de diferenciação de risco relativo (similar à taxa de risco, embora use uma diferença em vez de uma taxa). Uma diferença de risco é calculada subtraindo as incidências cumulativas de um item de dimensão (ou sobreposição com um segmento do gráfico de segmentos) de um segmento selecionado a partir de outro. Uma pontuação de diferença alta (próxima a 1) significa que um determinado item de dimensão ou segmento terciário era muito proeminente em um dos segmentos selecionados e não no outro.

>[!NOTE]
>
>Nos três gráficos, a estatística de diferença é baseada em uma amostra adequada de visitantes para fazer com que o processo seja executado da maneira mais rápida possível e se mantenha estatisticamente preciso. Embora a pontuação de diferença seja baseada em uma amostra, os resultados apresentados no gráfico não são amostras. Para garantir significância estatística, cada teste estatístico depende de um algoritmo de alocação dinâmico de maneira que o segmento menor contenha um tamanho de amostra que possua menos de 3% de margem de erro. Se um segmento contiver muito poucos visitantes (menos de 1.000), todos os dados disponíveis serão usados em vez da amostra para calcular a pontuação de diferenças.
