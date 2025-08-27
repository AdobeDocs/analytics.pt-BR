---
description: Quando um relatório tem muitos valores únicos, a Adobe usa o item de dimensão Tráfego baixo para melhorar o desempenho do relatório.
title: Valor de tráfego baixo no Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 42d044c3c56f13a232b721ef60f64bcf622ffa9f
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 8%

---

# Valor [!UICONTROL Tráfego baixo] no Adobe Analytics

Quando uma dimensão contém milhões de valores únicos, o Adobe fornece funcionalidade para garantir que os valores mais importantes sejam exibidos em seu relatório em tempo hábil. Valores únicos coletados além de um determinado limite são listados em um item de dimensão rotulado **[!UICONTROL Tráfego baixo]**.

O item de dimensão [!UICONTROL Tráfego baixo] permite que a Adobe garanta que os relatórios sejam retornados em tempo hábil, coletando valores únicos em excesso e agrupando-os.

Observe que a lógica [!UICONTROL Tráfego baixo] funciona melhor com dimensões que têm itens que se repetem muitas vezes durante o mês. Se os itens de dimensão forem quase ou totalmente exclusivos em cada ocorrência, o número de valores únicos atingirá o limite rapidamente e todos os valores subsequentes do mês terminarão no intervalo [!UICONTROL Tráfego baixo].

## Como os valores entram em [!UICONTROL Tráfego baixo]

Por padrão, um limite de **2.000.000 valores únicos** é definido por dimensão, por conjunto de relatórios e por mês do calendário. Os itens do Dimension que excedem esse limite de valor único são classificados em [!UICONTROL Tráfego baixo].

* Os itens do Dimension coletados antes da ocorrência do limite são calculados normalmente.
* Os itens de Dimension coletados após o limite ser excedido são classificados em [!UICONTROL Tráfego baixo].

>[!NOTE]
>A dimensão [Página](../components/dimensions/page.md) usa várias colunas de back-end que todas contam para o limite exclusivo, incluindo `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url` e `click_context`. Essas colunas de back-end podem fazer com que a lógica [!UICONTROL Tráfego baixo] seja aplicada bem antes que o número de itens de dimensão de Página exclusivos no Workspace atinja o limite.

O limite exclusivo de 2.000.000 pode ser alterado com base na dimensão. Consulte [Alterando limites exclusivos](#changing-unique-limit-thresholds) abaixo. No final de um mês, o número de valores únicos rastreados é redefinido globalmente.

## Como os valores podem escapar [!UICONTROL Tráfego baixo] depois de exceder o limite

Se uma determinada dimensão coletar mais de 2.000.000 valores únicos em um determinado mês, os itens de dimensão individuais poderão retornar ao relatório de seu próprio item de dimensão. O principal caso de uso desse recurso é permitir o relatório de itens de dimensão cruciais que podem receber um aumento de popularidade no final do mês após o limite único ser excedido. Por exemplo, se sua organização executar um site com milhões de artigos e um novo artigo se tornar popular no final do mês, você ainda poderá analisar o desempenho desse artigo. Essa lógica não tem como objetivo descompartimentar tudo o que obtém um determinado número de instâncias, mas oferecer uma maneira de analisar conteúdo que recebe um fluxo de tráfego.

Os requisitos para um item de dimensão individual escapar de [!UICONTROL Tráfego baixo] dependem de muitos fatores, muitos dos quais impedem a capacidade de calcular um limite exato:

* **Número de servidores processando dados para o conjunto de relatórios**: conjuntos de relatórios com mais tráfego exigem mais instâncias de um único item de dimensão para escapar [!UICONTROL Tráfego baixo].
* **Quantidade de tempo entre cada instância do item de dimensão**: as ocorrências que contêm um item de dimensão espalhado ao longo do dia exigem mais instâncias do que um pico concentrado de ocorrências.
* **Número de valores únicos para a dimensão**: cada dimensão tem um segundo limite definido como um valor de 2.100.000 valores únicos por padrão. Se o número de valores únicos em uma dimensão exceder esse limite mais alto, uma filtragem muito mais agressiva será aplicada.

Levando em consideração os fatores acima, espere **centenas a milhares** de instâncias para que um único item de dimensão escape [!UICONTROL Tráfego baixo] se apenas o primeiro limite for excedido. Espere de **milhares a dezenas de milhares** de instâncias para que um único item de dimensão escape [!UICONTROL Tráfego baixo] se o limite mais alto for excedido. A Adobe não garante que os itens de dimensão escapem de forma confiável do bucket [!UICONTROL Tráfego baixo]. Normalmente, esse conceito é reservado para itens de dimensão de alto volume fora do comum no final do mês.

Quando um item de dimensão escapa do bucket [!UICONTROL Tráfego baixo], as instâncias coletadas antes do fluxo de tráfego permanecem em [!UICONTROL Tráfego baixo].

## Alterar limites exclusivos

Às vezes, os limites podem ser alterados com base na dimensão. Entre em contato com o Atendimento ao cliente da Adobe ou com a equipe de contas da Adobe para solicitar essa alteração. A extensão em que os limites podem ser aumentados depende de vários fatores; a Adobe não garante que todas as solicitações de aumento de limite possam ser acomodadas. Ao solicitar uma alteração, inclua:

* A ID do conjunto de relatórios
* A dimensão para a qual você deseja aumentar o limite
* O primeiro e o segundo limites desejados:
   * O primeiro limite (classificação inicial) é definido como **2.000.000** por padrão.
   * O segundo limite (filtragem mais agressiva) está definido como **2,100,000** por padrão.

>[!IMPORTANT]
>
>Alterações nos limites podem afetar o desempenho do relatório. A Adobe recomenda avaliar bem a situação ao solicitar um aumento para valores únicos em uma dimensão. Aumente apenas os limites exclusivos para dimensões críticas para as necessidades de relatórios de sua organização.

Os limites [!UICONTROL Tráfego baixo] não estão visíveis na interface do usuário do Analytics. Entre em contato com o Atendimento ao cliente da Adobe se desejar obter mais informações sobre os limites.

## Interações com outros recursos

Recursos diferentes tratam valores de [!UICONTROL Tráfego baixo] de maneiras diferentes.

* **Data Warehouse:** na maioria dos casos, não há limite para o número de valores únicos nos relatórios do Data Warehouse. Sua arquitetura exclusiva permite o relatório de qualquer número de valores únicos. No entanto, os valores [!UICONTROL Tráfego baixo] ainda podem aparecer em alguns cenários limitados. Os exemplos incluem variáveis de lista, props de lista, eVars de merchandising e dimensões detalhadas de canal de marketing.
* **Segmentação:** se os critérios do segmento incluírem uma dimensão com um número alto de valores únicos, os valores capturados em [!UICONTROL Tráfego baixo] não serão incluídos.
* **Classificações:** os relatórios de classificação também estão sujeitos a limites únicos. Se um item de dimensão principal de uma classificação for incluído em [!UICONTROL Tráfego baixo], o valor não será classificado.
   * Valores de [!UICONTROL Tráfego baixo] classificados por meio do importador podem ser visualizados no Data Warehouse. <!-- AN-115871 -->
   * Valores de [!UICONTROL Tráfego baixo] classificados por meio do construtor de regras *não podem* ser exibidos no Data Warehouse. <!-- AN-122872 -->
