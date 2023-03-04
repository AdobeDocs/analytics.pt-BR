---
description: Quando um relatório tem muitos valores únicos, o Adobe usa o item de dimensão Tráfego baixo para melhorar o desempenho do relatório.
title: Valor de tráfego baixo no Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 49%

---

# Valor de tráfego baixo no Adobe Analytics

Quando um relatório tem muitos valores únicos, a Adobe fornece funcionalidade para garantir que os valores mais importantes sejam mostrados em seu relatório. Valores de variável únicos coletados após aproximadamente 500.000 valores existentes são listados em um item de dimensão rotulado **[!UICONTROL Tráfego baixo]**.

## Como o [!UICONTROL Tráfego baixo] funciona

* O relatório não é afetado se a variável não atingir 500.000 valores únicos em um determinado mês.
* Quando uma variável atinge 500.000 valores únicos, os dados começam a ser classificados em [!UICONTROL Tráfego baixo]. Cada valor além desse limite passa pela seguinte lógica:
   * Se um valor já estiver nos relatórios, adicione-o como de costume.
   * Se um valor ainda não for visto nos relatórios, ele será inicialmente classificado na variável [!UICONTROL Tráfego baixo] item de dimensão.
   * Se um valor for classificado em [!UICONTROL Tráfego baixo] O recebe um fluxo de tráfego (normalmente instâncias nos dígitos duplos em um único dia), e começa a ser reconhecido como seu próprio item de dimensão. As instâncias coletadas antes de atingir o limite permanecem abaixo [!UICONTROL Tráfego baixo]. O limite exato tem muitas dependências, como o número de servidores processando dados para o conjunto de relatórios e o tempo entre cada instância do item de dimensão.
* Se um conjunto de relatórios atingir mais de 1.000.000 valores únicos, uma filtragem mais agressiva será aplicada. Valores únicos exigem instâncias com os três dígitos em um único dia antes de serem reconhecidos como seu próprio item de dimensão.

Essa lógica permite que o Adobe otimize os recursos de relatórios e, ao mesmo tempo, permita que sua organização relate os itens de dimensão cruciais coletados no final do mês. Por exemplo, sua organização executa um site com milhões de artigos e um novo artigo se tornou popular no final do mês (depois de exceder ambos os limites únicos). Você ainda pode analisar o desempenho desse artigo sem que ele seja segmentado em [!UICONTROL Tráfego baixo]. Essa lógica não tem como objetivo remover tudo o que recebe um determinado número de exibições de página por dia ou por mês.

>[!NOTE]
>A variável [Página](../components/dimensions/page.md) A dimensão usa várias colunas de backend que todas contam para limites únicos, incluindo `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url`, e `click_context`. Essas colunas de backend podem causar [!UICONTROL Tráfego baixo] lógica a ser aplicada bem antes que o número de itens de dimensão de Página exclusivos no Workspace atinja 500.000.

## Alterar limites exclusivos

Os limites são de 500.000 e 1 milhão de valores únicos por padrão. Esses limites podem ser alterados para cada variável. Entre em contato com o Atendimento ao cliente da Adobe ou com a equipe de conta da Adobe para solicitar essa alteração. Ao solicitar uma alteração, inclua:

* A ID do conjunto de relatórios
* A variável para a qual você deseja aumentar o limite
* O primeiro e o segundo limites desejados

Alterações nos limites podem afetar o desempenho do relatório. A Adobe recomenda avaliar bem a situação ao solicitar um aumento para valores únicos em uma variável. Aumente apenas os limites exclusivos para variáveis críticas para as necessidades de relatórios de sua organização.

Os limites de tráfego baixo não estão visíveis na interface do usuário do Analytics. Entre em contato com o Atendimento ao cliente do Adobe se desejar obter mais informações sobre os limites existentes.

## Tráfego baixo usando componentes e outros recursos

Recursos diferentes tratam valores de tráfego baixo de maneiras diferentes.

* **Data Warehouse:** não há limite para o número de valores únicos nos relatórios do Data Warehouse. Sua arquitetura única permite gerar relatórios para qualquer número de valores únicos.
   * Em alguns cenários limitados, valores de tráfego baixo ainda podem aparecer. Os exemplos incluem vars de lista, props de lista, eVars de merchandising e dimensões detalhadas de canal de marketing.
* **Segmentação:** se os critérios do segmento incluírem uma variável com um número elevado de valores únicos, os valores capturados em Tráfego baixo não serão incluídos.
* **Classificações:** os relatórios de classificação também estão sujeitos a limites únicos. Se o valor da variável pai de uma classificação for incluído em Tráfego baixo, o valor não será classificado.
   * Valores de classificação de tráfego baixo obtidos por meio do importador podem ser visualizados no Data Warehouse. <!-- AN-115871 -->
   * Valores de classificação de tráfego baixo obtidos pelo construtor de regras *não podem* ser visualizados no Data Warehouse. <!-- AN-122872 -->
