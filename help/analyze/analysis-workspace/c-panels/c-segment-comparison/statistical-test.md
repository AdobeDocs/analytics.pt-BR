---
description: Cada um dos principais gráficos de comparação mostra uma pontuação de diferenças que é calculada de acordo com diversos testes estatísticos, dependendo da comparação que é feita. No entanto, independentemente do teste que for usado, a pontuação de diferenças é exibida como um valor entre 0 e 1.
keywords: Analysis Workspace;Segment IQ
title: Testes estatísticos usados na comparação entre segmentos
topic: Reports and analytics
uuid: c3f52470-5bfc-4e6b-8638-1c142b08d013
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Testes estatísticos usados na comparação entre segmentos

Cada um dos principais gráficos de comparação mostra uma pontuação de diferenças que é calculada de acordo com diversos testes estatísticos, dependendo da comparação que é feita. No entanto, independentemente do teste que for usado, a pontuação de diferenças é exibida como um valor entre 0 e 1.

Uma pontuação de 0 significa que não há diferença entre os dois segmentos e uma pontuação de 1 significa que houve uma diferença muito grande entre os dois segmentos. Há dois tipos de testes estatísticos empregados para gerar essas pontuações de diferença: para o quadro Principais métricas, é usado um teste Mann-Whitney U e para o quadro Principais itens de dimensão e Principais segmentos é usada uma comparação de diferença de risco.

## Pontuação de diferenças das principais métricas {#section_5E8047464EB945C78543B25F8F30F17A}

Na tabela Principais métricas, a Ferramenta de comparação entre segmentos usa um teste Mann-Whitney U de duas amostras, que é um teste de igualdade não paramétrica usado para comparar as distribuições de probabilidade unidimensionais de cada métrica para cada segmento considerado. A pontuação de diferença na tabela de métricas é uma combinação do valor p da estatística U computada (que representa a diferença estocasticamente entre os dois segmentos que são distribuídos por uma métrica específica) e a magnitude relativa da diferença observada. Uma grande pontuação de diferença (próxima a 1) significa que a métrica específica tem uma grande diferença relativa, bem como uma alta confiança estatística de que os segmentos são diferentes.

## Pontuação de diferenças nos principais itens de dimensão e nas principais diferenças entre segmentos {#section_8073ADA6053B44C9A23FDC5ED4AF2AC4}

Para calcular a pontuação de diferença nos quadros Principais itens de dimensão e Principais diferenças entre segmentos, é usado um algoritmo de diferenciação de risco relativo (semelhante à taxa de risco, embora usando uma diferença em vez de uma proporção). Uma diferença de risco é calculada subtraindo as incidências cumulativas de um item de dimensão (ou sobreposição com um segmento da tabela de segmentos) de um segmento selecionado do outro. Uma pontuação de diferença alta (próxima a 1) significa que o item de dimensão específico ou o segmento terciário foi muito importante em um dos segmentos selecionados e não no outro.

>[!NOTE] Nos três gráficos, a estatística de diferença é baseada em uma amostra adequada de visitantes para fazer com que o processo seja executado da maneira mais rápida possível e se mantenha estatisticamente preciso. Embora a pontuação de diferença seja baseada em uma amostra, os resultados apresentados na tabela não são amostrados. Para garantir significância estatística, cada teste estatístico depende de um algoritmo de alocação dinâmica, de modo que o segmento menor contenha um tamanho de amostra que ofereça menos de 3% de margem de erro. Se um segmento contiver poucos visitantes (menos de 1.000), usaremos todos os dados disponíveis e não obteremos uma amostra para calcular a pontuação de diferença.
