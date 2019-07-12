---
title: Relatórios de público-alvo no Adobe Analytics
description: Saiba como criar relatórios baseados em público-alvo usando a Analysis Workspace.
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# Relatórios de público-alvo

Os relatórios de público-alvo mostram informações sobre os tipos de pessoas que visitam seu site.

Esta página considera que o usuário tem um conhecimento básico sobre como usar a Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Usuários ativos

Os usuários ativos mostram o número cumulativo de usuários para o site nos últimos 1, 7, 14 ou 28 dias. Embora a Adobe não tenha o cálculo exato usado no Google Analytics, você pode usar a métrica Visitantes únicos para ver uma contagem desduplicada de usuários ao site com base no intervalo de datas selecionado.

Para obter um gráfico de linha de visitantes únicos:

1. Clique no ícone Visualizações à esquerda e arraste a visualização Linha até a área de trabalho acima da tabela vazia de forma livre.
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the smaller space labeled &#39;Drop a Metric here&#39;.
3. If different granularity is desired, drag the desired date range (e.g. **Day**, **Week**, **Month**, etc.) sobre o cabeçalho da dimensão de datas existente.

See [Unique Visitors](../../../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide for details on how Adobe calculates unique visitors.

## Valor de tempo de vida

O valor histórico é um recurso que requer implementação especializada adicional em ambas as plataformas. A Adobe recomenda trabalhar com um consultor de implementação para obter esses dados.

## Análise de coorte

A Análise de coorte mostra a frequência com que os mesmos usuários retornam ao site.

Para criar uma tabela de coorte:

1. Clique no ícone Visualização à esquerda e arraste a visualização da Tabela de coorte para a área de trabalho.
2. Click the Components icon on the left, then drag the **Visits** metric onto both the Inclusion Criteria and Return Criteria.
3. Clique em Construir.

See [Cohort Analysis](../../../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) in the Analysis Workspace user guide for details on additional customizations to the cohort visualization.

## Públicos-alvo

O relatório de Públicos-alvo no Google Analytics requer a configuração de públicos-alvo. Os públicos-alvo também exigem configuração na Adobe por meio do Adobe Audience Manager. Consulte o guia do usuário do Adobe Audience Manager para obter mais informações.

## User Explorer

O relatório do Usuário do Explorer permite que um analista visualize visitas individuais por meio de identificadores anônimos. A Adobe não coloca os identificadores de backend fora dos feeds de dados, que são exportações brutas de dados em nível de ocorrência.

* Se esses dados forem desejados na Analysis Workspace, será possível trabalhar com um consultor de implementação para passar o valor do cookie exclusivo de identificador anônimo em uma evar. Observe que isso só funciona com implementações menores que consistem de menos de 1 milhão de visitantes únicos por mês.
* If this data is desired within data feeds, the concatenated columns `visid_high` and `visid_low` are the most common way to identify unique visitors. Learn more about [Data Feeds](../../../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.

## Relatórios Demográficos e Interesses

Os dados demográficos e de interesses fornecem informações sobre idade, gênero e interesses dos usuários do site. Esses dados são coletados pelo Google por meio de suas capacidades de rastreamento entre sites.

Os dados demográficos e de interesses não são coletados automaticamente pela Adobe. No entanto, se a sua organização obtém esses dados, você pode usar Atributos do cliente, um recurso na plataforma Adobe Experience Cloud. Isso permite controlar totalmente a organização de dados por atributos, e não está limitada a apenas demografia ou interesses.

Consulte a Ajuda dos atributos do cliente para obter mais informações.

## Geo - Idioma

O relatório de idioma geográfico mostra o tráfego do site pela configuração de idioma no navegador do visitante.

Para criar um relatório de idioma:

1. In the Components menu, locate the **Language** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Language](../../../components/c-variables/dimensionslist/reports-languages.md) dimension in the Components user guide for more information.

## Localização geográfica - Local

O relatório de localização geográfica fornece uma exibição do mapa global, quebrando dados por país.

Para criar um relatório de localização geográfica:

1. Clique no ícone Visualizações à esquerda e arraste a visualização de Mapa para a área de trabalho acima da tabela vazia de forma livre.
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the space labeled &#39;Add Metric&#39;.
3. Clique em Construir.

Se a tabela também for desejada, além do mapa:

1. In the Components menu, locate the **Countries** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See [Geosegmentation](../../../components/c-variables/dimensionslist/reports-geosegmentation.md) dimensions in the Components user guide for more information.

## Comportamento - Novo vs. recorrente

O novo relatório vs recorrente fornece uma visualização simplificada das primeiras sessões (novas visitas) vs. sessões subsequentes (visitas de retorno).

Para criar um relatório de visitas novo e recorrente:

1. In the components menu, locate the **First Time Visits** segment and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;. Note that **First Time Visits** is a segment, while Workspace typically uses dimensions to represent rows.
2. Locate the **Return Visits** segment and drag it on top of the Segments row header. Isso adiciona o segmento como uma dimensão abaixo de Visitas pela primeira vez, permitindo uma comparação fácil.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Se um gráfico de linha também for desejado:

1. Clique no ícone de visualizações à esquerda e arraste uma visualização de Linha até a área de trabalho acima da tabela de forma livre
2. Use ctrl + clique (Windows) ou cmd + clique (Mac) em cada linha na tabela de forma livre para destacá-los. Isso permite que ambas as tendências sejam exibidas na visualização de linha.
3. Clique no ponto colorido pequeno no canto superior esquerdo da visualização da linha e clique na caixa de seleção «Bloquear seleção».

## Comportamento - Frequência e tempo decorrido

The frequency &amp; recency report is approximately equal to the **Visit Number** dimension in Analysis Workspace.

1. In the components menu, locate the **Visit Number** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Visit Number](../../../components/c-variables/dimensionslist/reports-visitor-number.md) dimension in the Components user guide for more information.

## Comportamento - Envolvimento

The engagement report is approximately equal to the **Time Spent per Visit - Bucketed** dimension.

1. In the components menu, locate the **Time Spent per Visit - Bucketed** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Time Spent per Visit](../../../components/c-variables/dimensionslist/reports-time-spent-per-visit.md) dimension in the Components user guide for more information.

## Tecnologia - Navegador e SO

Há várias dimensões primárias disponíveis no relatório Navegador e SO.

* The **Browser** primary dimension is also available in Analysis Workspace as a dimension.
* The **Operating System** primary dimension is also available in Analysis Workspace as a dimension.
* The **Screen Resolution** primary dimension is available in Analysis Workspace as the **Monitor Resolution** dimension.
* The **Screen Colors** primary dimension is available in Analysis Workspace as the **Color Depth** dimension.
* The **Flash Version** primary dimension is not available in Adobe Analytics, however this data can be collected by an eVar if wanted.

1. No menu de componentes, localize a dimensão desejada acima e arraste-a para a grande área de tabela de forma livre denominada &quot;Soltar uma dimensão aqui&quot;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Consulte as seguintes páginas no guia do usuário Componentes para obter mais informações sobre sua respectiva dimensão:

* [Navegador](../../../components/c-variables/dimensionslist/reports-browsers.md)
* [Sistema operacional](../../../components/c-variables/dimensionslist/reports-operating-system.md)
* [Resolução do Monitor](../../../components/c-variables/dimensionslist/reports-technology.md)
* [Intensidade de cor](../../../components/c-variables/dimensionslist/reports-color-depth.md)

## Tecnologia - Rede

The network report is approximately equal to the **Domain** dimension.

1. In the components menu, locate the **Domain** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Domain](../../../components/c-variables/dimensionslist/reports-domains.md) dimension in the Components user guide for more information.

## Móvel - Visão geral

The mobile overview report is approximately equal to the **Mobile Device Type** dimension. Observe que o valor «Outros» equivale ao tráfego da área de trabalho.

1. In the components menu, locate the **Mobile Device Type** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device Type](../../../components/c-variables/dimensionslist/reports-device-types.md) dimension in the Components user guide for more information.

## Dispositivos móveis - Dispositivos

The mobile devices report is approximately equal to the **Mobile Device** dimension.

1. In the components menu, locate the **Mobile Device** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device](../../../components/c-variables/dimensionslist/reports-devices.md) dimension in the Components user guide for more information.

## Personalizado 

Os relatórios personalizados são definidos com base em cada implementação. Entre em contato com o administrador e/ou o consultor de implementação do Analytics para interpretar esses relatórios. Typically an organization maintains a [Solution Design Document](../../../implement/prepare/solution-design.md) to keep track of custom variable values and how they are populated.

## Benchmarking

Os relatórios de comparação permitem que você veja como as facetas de seus dados se comparam às médias do setor. No momento, a Adobe não compartilha dados de benchmarking entre seus clientes.

## Fluxo de usuários

O relatório de fluxo está disponível em ambas as plataformas. Para criar um relatório de fluxo:

1. Clique no ícone de visualizações à esquerda e arraste uma visualização de Fluxo até a área de trabalho acima da tabela de forma livre
2. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. Os valores de dimensão são coloridos amarelos.
3. Localize o valor da página desejada para começar e arraste-o para o espaço denominado &quot;Dimensão ou item&quot; no centro
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito para expandir ou recolher colunas. Diferentes dimensões também podem ser usadas no mesmo relatório de fluxo.
