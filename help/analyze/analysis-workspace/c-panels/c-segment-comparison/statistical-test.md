---
description: Cada um dos principais gráficos de comparação mostra uma pontuação de diferença que é calculada por diversos testes estatísticos dependendo da comparação que é feita; no entanto, independentemente do teste que for usado, a pontuação de diferença é exibida como um valor entre 0 e 1.
keywords: Analysis Workspace; IQ do segmento
seo-description: Cada um dos principais gráficos de comparação mostra uma pontuação de diferença que é calculada por diversos testes estatísticos dependendo da comparação que é feita; no entanto, independentemente do teste que for usado, a pontuação de diferença é exibida como um valor entre 0 e 1.
seo-title: Testes estatísticos usados na comparação de segmentos
solution: Analytics
title: Testes estatísticos usados na comparação de segmentos
topic: Reports and Analytics
uuid: c 3 f 52470-5 bfc -4 e 6 b -8638-1 c 142 b 08 d 013
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Testes estatísticos usados na comparação de segmentos

Cada um dos principais gráficos de comparação mostra uma pontuação de diferença que é calculada por diversos testes estatísticos dependendo da comparação que é feita; no entanto, independentemente do teste que for usado, a pontuação de diferença é exibida como um valor entre 0 e 1.

Uma pontuação igual a 0 significa que não há diferença entre os dois segmentos e uma pontuação igual a 1 significa que há uma grande diferença entre os dois segmentos. Há dois tipos de testes estatísticos implantados para gerar essas pontuações de diferenciação: para o gráfico Principais métricas, um teste Mann-Whitney U é usado e para os gráficos Principais itens de dimensão e Principais segmentos é usada uma comparação de diferença de risco.

## Top metrics difference score {#section_5E8047464EB945C78543B25F8F30F17A}

No gráfico Principais métricas, a Ferramenta comparação entre segmentos usa um teste Mann-Whitney U com duas amostras, que é um teste de igualdade não paramétrica para comparar as distribuições de probabilidade de uma dimensão de cada métrica para cada segmento considerado. A pontuação de diferença no gráfico de métricas é uma combinação do valor p da estatística U computada (que representa a maneira diferente que os dois segmentos são distribuídos em uma determinada métrica) e a magnitude relativa da diferença observada. Uma pontuação de diferença grande (próxima a 1) significa que a métrica possui uma diferença relativa considerável, bem como uma confiança estatística indicando que os dois segmentos são diferentes.

## Top dimension items and top segments difference scores {#section_8073ADA6053B44C9A23FDC5ED4AF2AC4}

Para computar a pontuação de diferença nos gráficos Principais itens de dimensão e Principais diferenças entre segmentos, é usado um algoritmo de diferenciação de risco relativo (similar à taxa de risco, embora use uma diferença em vez de uma taxa). Uma diferença de risco é calculada subtraindo as incidências cumulativas de um item de dimensão (ou sobreposição com um segmento do gráfico de segmentos) de um segmento selecionado a partir de outro. Uma pontuação de diferença alta (próxima a 1) significa que o item de dimensão particular ou o segmento terciário era muito importante em apenas um dos segmentos selecionados.

>[!NOTE]
>
>Nas três tabelas, a estatística de diferença é baseada em uma amostra adequada de visitantes para fazer com que o processo seja executado o mais rápido possível, enquanto permanece estatisticamente preciso. Embora a pontuação de diferença seja baseada em uma amostra, os resultados apresentados no gráfico não são amostras. Para garantir significância estatística, cada teste estatístico depende de um algoritmo de alocação dinâmico de maneira que o segmento menor contenha um tamanho de amostra que possua menos de 3% de margem de erro. Se um segmento contém pouco visitantes (menos de 1.000), nós usamos todos os dados disponíveis e não criamos uma amostra para computar a pontuação de diferença.

