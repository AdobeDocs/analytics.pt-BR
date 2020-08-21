---
title: Analisar Canais de marketing
description: Saiba como usar dimensões de Canais de marketing no Workspace.
translation-type: ht
source-git-commit: 586dabe8454bb2e6fbd4f3fbdb18d13a18b0417d
workflow-type: ht
source-wordcount: '407'
ht-degree: 100%

---


# Analisar Canais de marketing

Você provavelmente quer saber qual de seus canais de marketing é o mais eficiente, e para quem, para que você possa direcionar seus esforços e receber um melhor retorno sobre o investimento feito em marketing. No Adobe Analytics, as dimensões e métricas dos Canais de marketing no Workspace são uma das ferramentas que podem ajudar você a rastrear a influência de canais diferentes em seus pedidos, receita etc. e fornecer insights úteis sobre o canal. Estas são as dimensões e métricas que você pode usar relacionadas aos Canais de marketing:

![](assets/mc-dims.png)

| Dimensão/métrica | Definição |
|---|---|
| Canal de Marketing | Esta é a dimensão recomendada para usar nos canais de marketing. Os modelos de Attribution IQ podem ser aplicados a ele no tempo de execução. Essa dimensão se comporta de forma idêntica à dimensão Canal de último contato, mas é rotulada de maneira diferente para evitar confusão ao usá-la com um modelo de atribuição diferente. |
| Canal de último contato | Dimensão herdada, com modelo de atribuição de último contato pré-aplicado e inalterável. |
| Canal de primeiro contato | Dimensão herdada, com modelo de atribuição de primeiro contato pré-aplicado e inalterável. |
| Instâncias do canal de marketing | Essa métrica mede o número de vezes que um canal de marketing foi definido em uma solicitação de imagem, incluindo visualizações de página padrão e chamadas de link personalizadas. Não inclui valores persistentes. |
| Novos engajamentos | Essa métrica é semelhante a Instâncias, mas só é aumentada quando o canal de marketing de primeiro contato é definido em uma solicitação de imagem. |

## Análise básica

Esta tabela de forma livre mostra as métricas Pedidos online, Receita online e a Taxa de conversão para cada Canal de marketing:

![](assets/mc-viz1.png)

Aqui você vê cada Pedido online de Canais de marketing e Receita online em um gráfico de rosca:

![](assets/mc-viz2.png)

Este gráfico de Linha mostra as tendências em Pedidos Online para vários canais ao longo do tempo:

![](assets/mc-viz3.png)

## Análise avançada

Os Detalhes dos canais de marketing aprofundam-se em cada canal para mostrar campanhas, disposições etc. específicas. Você pode dividir cada Canal de marketing em detalhes:

![](assets/mc-viz4.png)

## Aplicar modelos de atribuição

Você pode usar o [Attribution IQ](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/panels/attribution.html) para aplicar modelos de atribuição diferentes instantaneamente:

![](assets/mc-viz5.png)

Observe como a mesma métrica (Pedidos online) gera resultados diferentes quando você aplica modelos de atribuição diferentes.

Estes são alguns vídeos explicando o Attribution IQ com mais detalhes: [Lista de reprodução do Attribution IQ](https://www.youtube.com/playlist?list=PL2tCx83mn7GuDzYEZ8jQlaScruZr3tBTR).

## Análise de marketing entre guias

Usando o Canal de primeiro contato e o Canal de último contato herdados, você pode obter uma visualização útil nas interações do canal:

![](assets/mc-viz6.png)

Saiba mais sobre a análise de marketing entre guias [neste vídeo](https://www.youtube.com/watch?v=M3EOdONa-3E).
