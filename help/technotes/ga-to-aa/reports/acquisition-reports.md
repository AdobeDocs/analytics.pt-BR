---
title: Relatórios de aquisição no Adobe Analytics
description: Saiba como criar relatórios baseados em aquisição usando a Analysis Workspace.
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# Relatórios de aquisição

Os relatórios de aquisição mostram como você obtém visitantes ao site.

In Adobe Analytics, these reports are known as **Marketing Channels**. Eles exigem uma configuração inicial básica, mas permitem uma visualização muito mais personalizada dos canais.

> [!IMPORTANT]
>
> Configure suas regras de processamento do Canal de marketing para usar esses relatórios. See [Getting Started with Marketing Channels](../../../components/c-marketing-channels/c-getting-started-mchannel.md) for information on how to best configure Marketing Channels in your organization.

Esta página considera que o usuário tem um conhecimento básico sobre como usar a Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Todo o tráfego - Canais

Mostra uma exibição agregada de todos os canais que os visitantes usam para chegar ao site.

1. In the Components menu, locate the **Marketing Channel** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Todo o tráfego - Mapas de árvore

Mostra um mapa de árvore do tráfego de canal. Este relatório é semelhante a Todo o tráfego - Canais, mas é mostrado de maneira diferente.

1. Clique no ícone Visualizações à esquerda e arraste a visualização de Treemap para a área de trabalho acima da tabela vazia de forma livre.
2. Click the Components icon on the left, then drag the **Marketing Channel** dimension onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.
4. Observe que as métricas adicionais criam mapas de árvore adicionais. Se apenas um mapa de árvore for desejado:
   1. Clique na célula superior da métrica desejada para representar o mapa de árvore.
   2. Clique com a tecla Shift pressionada na última célula da mesma coluna de métrica para realçar a coluna azul. Se feito corretamente, um mapa de árvore estará presente na visualização.
   3. Clique no ponto colorido no canto superior direito da visualização de treemap e clique na caixa de seleção&#39;Bloquear seleção &#39;.

Os mapas de árvore podem ser aplicados a qualquer dimensão, não apenas os Canais de marketing.

## Todo o tráfego - Fonte/Meio

Os relatórios de origem e mídia mostram os domínios que direcionam o tráfego para o site.

* The **Source** primary dimension is available in Analysis Workspace as the **Referring Domain** dimension.
* The **Medium** primary dimension is available in Analysis Workspace as the  **Referrer Type** dimension.
* The **Keyword** primary dimension is available in Analysis Workspace as the **Search Keyword** dimension.

1. No menu de componentes, localize a dimensão desejada acima e arraste-a para a grande área de tabela de forma livre denominada &quot;Soltar uma dimensão aqui&quot;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

Consulte as seguintes páginas no guia do usuário Componentes para obter mais informações sobre sua respectiva dimensão:

* [Domínio de referência](../../../components/c-variables/dimensionslist/reports-referring-domains.md)
* [Tipo de referenciador](../../../components/c-variables/dimensionslist/reports-ref-types.md)
* [Palavra-chave de pesquisa](../../../components/c-variables/dimensionslist/reports-search-keywords.md)

## Todo o tráfego - Referências

* The **Source** primary dimension is available in Analysis Workspace as the **Referring Domain** dimension.
* The **Landing Page** primary dimension is available in Analysis Workspace as the **Entry Page** dimension.

1. In the components menu, locate the **Referring Domain** or **Entry Page** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Referring Domain](../../../components/c-variables/dimensionslist/reports-referring-domains.md) dimension in the Components user guide for more information.

## Relatórios do Google Ads e relatórios do Console de pesquisa

A Adobe usa um recurso na Analysis Workspace chamada Advertising Analytics para trazer os dados de publicidade e pesquisa de várias plataformas, incluindo o Google.

O recurso de análise de publicidade requer a configuração de retorno de dados. See [Advertising Analytics Help](../../../integrate/c-advertising-analytics/overview.md) for details on how to enable these additional dimensions in Analysis Workspace.

## Relatórios Social 

Os relatórios do Social fornecem informações semelhantes como seu respectivo relatório de Comportamento, exceto no contexto de redes sociais. Esses dados estão disponíveis na Analysis Workspace combinando uma dimensão com um segmento.

Às vezes, os visitantes chegam ao site por meio de vários canais na mesma sessão. Por exemplo, um visitante clica em uma página de mídia social, em seguida, alguns minutos depois visita um mecanismo de pesquisa para acessar o site. Nesses casos, os domínios não sociais podem aparecer neste relatório. Se você deseja excluir domínios não sociais, classifique o relatório por visitas ou crie uma cópia do segmento para que se baseie nas ocorrências em vez de visitas. See [Segmentation Containers](../../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

### Social - Referências de rede

O relatório de Referenciadores de rede mostra quais domínios de rede social direcionam o tráfego para o site. This data is available in Analysis Workspace using the **Referring Domain** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Referring Domain** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled &#39;Drop a segment here&#39;.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social - Páginas de aterrissagem

O relatório de Páginas de aterrissagem mostra quais páginas chegaram após clicar em um link por uma rede social. This data is available in Analysis Workspace using the **Entry Page** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled &#39;Drop a segment here&#39;.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social - Conversões

O relatório de Conversões mostra dados de comércio eletrônico no contexto de redes sociais. É necessária uma implementação adicional para usar esses relatórios em ambas as plataformas; A Adobe recomenda trabalhar com um consultor de implementação para garantir que esses dados estejam configurados corretamente para a Analysis Workspace.

### Social - Plug-ins

O relatório de plug-ins mostra como os visitantes interagem com plug-plugins de mídia social incorporados em seu site. A implementação adicional é necessária para uso na Analysis Workspace. A Adobe recomenda trabalhar com um consultor de implementação para garantir que esses dados sejam coletados com precisão.

### Social - Fluxo de usuários

O relatório de fluxo de usuários mostra os dados de definição de caminho no contexto de visitantes que chegam por meio de uma rede social.

1. Clique no ícone de visualizações à esquerda e arraste uma visualização de Fluxo até a área de trabalho acima da tabela de forma livre
2. Click the Components icon on the left, then drag the **Visits from Social Sites** segment onto the small area just above the flow visualization labeled &#39;Drop a Segment here&#39;.
3. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. Os valores de dimensão são coloridos amarelos.
4. Localize o valor da página desejada para começar e arraste-o para o espaço denominado &quot;Dimensão ou item&quot; no centro
5. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito para expandir ou recolher colunas. Diferentes dimensões também podem ser usadas no mesmo relatório de fluxo.

## Campanhas - Todas

The campaigns report is available in Analysis Workspace using the **Tracking Code** dimension. Observe que o uso da dimensão Código de rastreamento requer uma implementação adicional para coletar dados.

É possível coletar parâmetros UTM no Adobe Analytics usando variáveis personalizadas (evars). A Adobe recomenda trabalhar com um consultor de implementação para garantir que os valores de código de rastreamento sejam coletados precisamente no Adobe Analytics.

1. In the Components menu, locate the **Tracking Code** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Campanhas - Palavras-chave pagas

O relatório de palavras-chave pagas mostra como cada palavra-chave ocorre depois que um visitante clica em um link de pesquisa pago de um mecanismo de pesquisa. The **Search Keywords - Paid** dimension is available in Analysis Workspace, but requires a one-time setup of paid search detection to collect data. See [Paid Search Detection](../../../admin/admin/paid-search-detection/paid-search-detection.md) in the Admin user guide for setup details.

1. In the Components menu, locate the **Search Keyword - Paid** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Campanhas - Palavras-chave orgânicas

O relatório de palavras-chave orgânicas mostra como cada palavra-chave ocorre depois que um visitante clica em um link de pesquisa orgânico de um mecanismo de pesquisa. The **Search Keywords - Natural** dimension is available in Analysis Workspace. Observe que, se a detecção de pesquisa paga não estiver configurada, essa dimensão coleta palavras-chave pagas e naturais.

1. In the Components menu, locate the **Search Keyword - Natural** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## Análise de custo

Este relatório mostra os dados de desempenho de visitas, custo e receita para os canais de marketing pagos. A Adobe fornece um produto dedicado para fornecer insight chamado Adobe Advertising Cloud. Se sua organização estiver interessada em usar este produto, entre em contato com o Gerente de conta de sua organização.
