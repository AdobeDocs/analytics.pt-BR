---
title: Práticas recomendadas para implementar os Canais de marketing do Adobe Analytics
description: Práticas recomendadas atualizadas para usar os Canais de marketing com o Attribution IQ e o Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 402546c3110e78240e9379ea28957b070f22e697
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 3%

---


# Attribution IQ com Canais de marketing - Práticas recomendadas

[Os ](/help/components/c-marketing-channels/c-getting-started-mchannel.md) Canais de marketing são um recurso valioso e poderoso do Adobe Analytics. As orientações atuais sobre a implementação do Marketing Channel foram formuladas em um momento em que não existia [Attribution IQ](https://experienceleague.corp.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en#analysis-workspace) nem [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=pt-BR#cja-usecases).

Para garantir a sua implementação de Canais de marketing e a consistência dos relatórios com o Attribution IQ e o Customer Journey Analytics, estamos emitindo um conjunto de práticas recomendadas atualizadas. Se você já estiver usando os Canais de marketing, poderá escolher as melhores opções entre essas novas diretrizes. Se você nunca usou os Canais de marketing, recomendamos que siga todas as novas práticas recomendadas.

Quando os Canais de marketing foram introduzidos pela primeira vez, eles só tinham as dimensões de primeiro e último toque. As dimensões explícitas de primeiro/último toque não são mais necessárias com a versão atual da atribuição. O Adobe fornece dimensões genéricas de &quot;Canal de marketing&quot; e &quot;Detalhe do canal de marketing&quot; para que você possa usá-las com o modelo de atribuição desejado. Essas dimensões genéricas se comportam de forma idêntica às dimensões do Canal de último toque, mas são rotuladas de forma diferente para evitar confusão ao usar Canais de marketing com um modelo de atribuição diferente.

Como as dimensões do Canal de marketing dependem de uma definição de Visita tradicional (conforme definido por suas regras de processamento), elas não podem ser alteradas usando Conjuntos de relatórios virtuais. Essas práticas revisadas permitem janelas de pesquisa claras e controladas com o Attribution IQ e com o CJA.

## Prática recomendada nº 1: Aproveite o Attribution IQ para análise controlada

Recomendamos usar [Attribution IQ](https://experienceleague.corp.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=en#analysis-workspace) em vez da atribuição existente do Canal de marketing para ajustar a análise do Canal de marketing. Siga as outras práticas recomendadas para garantir a consistência e os controles robustos da sua análise com o Attribution IQ.

![](assets/attribution.png)

* A configuração das dimensões Canal de marketing e Detalhe de canal de marketing estabelece pontos de contato a serem avaliados, de acordo com cada Instância de canal de marketing.
* Para análise de métrica, sua organização deve se alinhar em um ou mais modelos de atribuição. Salve métricas personalizadas com este modelo para reutilização fácil.
* Por padrão, os dados são alocados usando Último contato e a configuração do Período de envolvimento do visitante. Os modelos de métricas de Attribution IQ oferecem maior controle sobre as janelas de retrospectiva e mais variedade, incluindo [atribuição algorítmica](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/algorithmic.html?lang=en#analysis-workspace).

## Prática recomendada nº 2: Nenhuma definição de canal de Atualização direta e de Sessão

Os canais de Atualização direta e interna/sessão não são recomendados para uso com modelos de atribuição personalizados (Attribution IQ).

E se sua organização já tiver as opções Direct e Session Refresh configuradas? Nesse caso, recomendamos que você crie uma classificação para seus Canais de marketing e deixe esses dois canais não classificados. A dimensão classificada produzirá os mesmos resultados de Attribution IQ que se esses canais nunca tivessem sido configurados.

![](assets/direct-session-refresh.png)

## Prática recomendada nº 3: Habilitar Substituir canal de último toque para todos os canais

Modelos de atribuição personalizados usados com a dimensão Canal de marketing no Workspace funcionam melhor quando essa configuração é ativada. Habilitar essa configuração faz com que uma Instância de Canal de marketing seja contabilizada quando um novo canal/detalhe for encontrado. Você deve ativar isso para todos os canais, exceto para Atualização direta ou interna/sessão, que não é mais recomendado para uso com modelos de atribuição personalizados (Attribution IQ).

![](assets/override.png)

## Prática recomendada nº 4: Minimizar o período de envolvimento do visitante

Definir o período de Envolvimento do Visitante para o mínimo de &quot;1 dia&quot; minimiza a probabilidade de valores persistentes. Como os modelos de atribuição personalizados (AIQ) permitem janelas de retrospectiva flexíveis, recomendamos definir o valor mínimo para minimizar o impacto dessa configuração.

![](assets/expiration.png)

## Prática recomendada nº 5: As Regras de processamento de canais de marketing devem existir somente para canais ativados

Remova quaisquer Regras de processamento de canal de marketing para canais desativados. As regras devem existir somente para Canais de marketing que estejam marcados como ativados.
