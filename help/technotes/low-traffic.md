---
description: Quando um relatório tem muitos valores únicos, a Adobe usa o item de dimensão Tráfego baixo para melhorar o desempenho do relatório.
title: Valor de tráfego baixo no Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: f242ec6613cf046224f76f7edc7813a34c65fff8
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 77%

---

# Valor de tráfego baixo no Adobe Analytics

Quando um relatório tem muitos valores únicos, a Adobe fornece funcionalidade para garantir que os valores mais importantes sejam mostrados em seu relatório. Valores únicos de variáveis coletados além de um determinado limite (veja abaixo) são listados em um item de dimensão rotulado **[!UICONTROL Tráfego baixo]**.

## Como o [!UICONTROL Tráfego baixo] funciona

* O Adobe Analytics usa dois limites para determinar quais valores únicos são exibidos nos relatórios a cada mês: **[!UICONTROL limite baixo]** e um **[!UICONTROL limite alto]**. Esses limites podem ser ajustados por Adobe de tempos em tempos. Os limites atuais são:
   * **[!UICONTROL Limite baixo]**: 2.000.000 valores únicos durante o mês.
   * **[!UICONTROL Limite alto]**: 2.100.000 valores únicos durante o mês.
* O relatório não é afetado se uma variável não atingir o limite baixo em um determinado mês.
* Quando uma variável atinge o limite baixo, os dados começam a ser classificados em um item de dimensão rotulado [!UICONTROL Tráfego baixo]. Cada valor além desse limite passa pela seguinte lógica:
   * Se um valor já estiver nos relatórios, adicione-o como de costume.
   * Se um valor ainda não for visto nos relatórios, adicione-o inicialmente ao item de dimensão [!UICONTROL Tráfego baixo].
   * Se um valor classificado em [!UICONTROL Tráfego baixo] receber um fluxo de tráfego (normalmente instâncias nos dígitos duplos em um único dia), reconheça-o como seu próprio item de dimensão. As instâncias coletadas antes do fluxo de tráfego permanecem em [!UICONTROL Tráfego baixo]. O ponto exato em que o item de dimensão começa a ser exibido nos relatórios depende de vários fatores, como o número de servidores processando dados para o conjunto de relatórios e o tempo entre cada instância do item de dimensão.
* Se uma variável atingir o limite superior, uma filtragem mais agressiva será aplicada. Valores exclusivos exigem instâncias de três dígitos em um único dia antes de serem reconhecidos como seu próprio item de dimensão.

Essa lógica permite que a Adobe otimize os recursos de relatórios e, ao mesmo tempo, permita que sua organização gere relatórios sobre itens de dimensões fundamentais coletados no final do mês. Por exemplo, se sua organização executar um site com milhões de artigos e um novo artigo se tornar popular no final do mês (depois de exceder ambos os limites únicos), ainda será possível analisar o desempenho desse artigo sem que ele seja agrupado em [!UICONTROL Tráfego baixo]. Essa lógica não tem como objetivo desagrupar tudo que obtém um determinado número de visualizações de página por dia ou por mês.

>[!NOTE]
>A dimensão [Página](../components/dimensions/page.md) usa várias colunas de back-end que contam para limites exclusivos, incluindo `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url` e `click_context`.  Essas colunas de back-end podem fazer com que a lógica [!UICONTROL Tráfego baixo] seja aplicada bem antes que o número de itens de dimensão de página exclusivos no Workspace atinja o limite inferior.

Observe que a lógica de tráfego baixo funciona melhor com variáveis que têm itens de dimensão que se repetem muitas vezes durante o mês. Se os itens de dimensão de uma variável forem quase ou totalmente exclusivos em cada ocorrência, o número de valores únicos da variável atingirá ambos os limites rapidamente e todos os itens de dimensão subsequentes do mês acabarão na classificação de tráfego baixo.

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
