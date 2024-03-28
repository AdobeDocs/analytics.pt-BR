---
description: Quando um relatório tem muitos valores únicos, a Adobe usa o item de dimensão Tráfego baixo para melhorar o desempenho do relatório.
title: Valor de tráfego baixo no Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: fe6b1a2d503bbc423d3ebcacad2ce3c29e1ebbed
workflow-type: ht
source-wordcount: '864'
ht-degree: 100%

---

# Valor de tráfego baixo no Adobe Analytics

Quando um relatório tem muitos valores únicos, a Adobe fornece funcionalidade para garantir que os valores mais importantes sejam mostrados em seu relatório. Valores únicos de variáveis coletados além de um determinado limite (veja abaixo) são listados em um item de dimensão rotulado **[!UICONTROL Tráfego baixo]**.

## Como o [!UICONTROL Tráfego baixo] funciona

* O Adobe Analytics usa dois limites para determinar quais valores únicos são exibidos nos relatórios a cada mês: **[!UICONTROL limite baixo]** e um **[!UICONTROL limite alto]**. Esses limites podem ser ajustados pela Adobe de tempos em tempos. Os limites atuais são:
   * **[!UICONTROL Limite baixo]**: > 500.000 valores únicos durante o mês.
   * **[!UICONTROL Limite alto]**: > 1.000.000 valores únicos durante o mês.
* Em **meados de abril de 2024**, a Adobe começará a aumentar os limites padrão de tráfego baixo para conjuntos de relatórios da seguinte maneira: ![limites de tráfego baixo](assets/thresholds.png)
Isso afetará somente as variáveis que estão definidas abaixo dos novos limites. Essas alterações serão feitas de forma incremental e esperamos que o trabalho seja concluído até o **fim de maio**. À medida que esses aumentos forem implementados, você poderá notar alterações nas variáveis de alta cardinalidade:<ul><li>Mais valores de dimensão podem estar disponíveis para relatórios.</li><li>Segmentos e métricas calculadas podem incluir mais dados.</li><li>Os conjuntos de relatórios virtuais baseados em segmentos podem incluir mais dados.</li><li>As exportações de classificação podem incluir mais dados.</li></ul>
* Os relatórios não são afetados se a variável não atingir o limite inferior num determinado mês.
* Quando uma variável atinge o limite inferior, os dados começam a ser agrupados em [!UICONTROL Tráfego baixo]. Cada valor além desse limite passa pela seguinte lógica:
   * Se um valor já estiver nos relatórios, adicione-o como de costume.
   * Se um valor ainda não for visto nos relatórios, ele será inicialmente agrupado no item de dimensão [!UICONTROL Tráfego baixo].
   * Se um valor agrupado em [!UICONTROL Tráfego baixo] receber um influxo de tráfego (normalmente instâncias de dois dígitos em um único dia), ele começará a ser reconhecido como seu próprio item de dimensão. As instâncias coletadas antes de atingir o limite permanecem em [!UICONTROL Tráfego baixo]. O ponto exato em que o item de dimensão começa a ser exibido nos relatórios depende de vários fatores, como o número de servidores processando dados para o conjunto de relatórios e o tempo entre cada instância do item de dimensão.
* Se uma variável atingir o limite superior, uma filtragem mais agressiva será aplicada. Valores exclusivos exigem instâncias de três dígitos em um único dia antes de serem reconhecidos como seu próprio item de dimensão.

Essa lógica permite que a Adobe otimize os recursos de relatórios e, ao mesmo tempo, permita que sua organização gere relatórios sobre itens de dimensões fundamentais coletados no final do mês. Por exemplo, se sua organização executar um site com milhões de artigos e um novo artigo se tornar popular no final do mês (depois de exceder ambos os limites únicos), ainda será possível analisar o desempenho desse artigo sem que ele seja agrupado em [!UICONTROL Tráfego baixo]. Essa lógica não tem como objetivo desagrupar tudo que obtém um determinado número de visualizações de página por dia ou por mês.

>[!NOTE]
>A dimensão [Página](../components/dimensions/page.md) usa várias colunas de back-end que contam para limites exclusivos, incluindo `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url` e `click_context`.  Essas colunas de back-end podem fazer com que a lógica [!UICONTROL Tráfego baixo] seja aplicada bem antes que o número de itens de dimensão de página exclusivos no Workspace atinja o limite inferior.

Observe que a lógica de tráfego baixo descrita acima funciona melhor com variáveis que têm itens de dimensão que se repetem muitas vezes durante o mês. Se os itens de dimensão de uma variável forem quase ou totalmente únicos em cada ocorrência, a variável atingirá o limite baixo rapidamente e todos os novos itens de dimensão do mês acabarão no agrupamento de tráfego baixo.

## Alterar limites exclusivos

Esses limites podem ser alterados para cada variável individualmente. Entre em contato com o Atendimento ao cliente da Adobe ou com a equipe de contas da Adobe para solicitar essa alteração. O grau de aumento desses limites depende de vários fatores, e pode ser que a Adobe não consiga acomodar aumentos de limite em todos os casos. Ao solicitar uma alteração, inclua:

* A ID do conjunto de relatórios
* A variável para a qual você deseja aumentar o limite
* O primeiro e o segundo limites desejados

Alterações nos limites podem afetar o desempenho do relatório. A Adobe recomenda usar o bom senso ao solicitar um aumento de valores exclusivos em uma variável. Aumente apenas os limites exclusivos para variáveis críticas para as necessidades de relatórios da sua organização.

Os limites de tráfego baixo não estão visíveis na interface do Analytics. Entre em contato com o Atendimento ao cliente da Adobe se desejar obter mais informações sobre os limites.

## Tráfego baixo usando componentes e outros recursos

Recursos diferentes tratam valores de tráfego baixo de maneiras diferentes.

* **Data Warehouse:** não há limite para o número de valores únicos nos relatórios do Data Warehouse. Sua arquitetura única permite gerar relatórios para qualquer número de valores únicos.
   * Em alguns cenários limitados, valores de tráfego baixo ainda podem aparecer. Os exemplos incluem vars de lista, props de lista, eVars de merchandising e dimensões detalhadas de canal de marketing.
* **Segmentação:** se os critérios do segmento incluírem uma variável com um número elevado de valores únicos, os valores capturados em Tráfego baixo não serão incluídos.
* **Classificações:** os relatórios de classificação também estão sujeitos a limites únicos. Se o valor da variável pai de uma classificação for incluído em Tráfego baixo, o valor não será classificado.
   * Valores de classificação de tráfego baixo obtidos por meio do importador podem ser visualizados no Data Warehouse. <!-- AN-115871 -->
   * Valores de classificação de tráfego baixo obtidos pelo construtor de regras *não podem* ser visualizados no Data Warehouse. <!-- AN-122872 -->
