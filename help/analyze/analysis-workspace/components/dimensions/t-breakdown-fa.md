---
description: Analise dimensões e itens de dimensão no Analysis Workspace.
keywords: Analysis Workspace
title: Analisar dimensões
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: ed4d7bb2b3ba290da575ce18fa6ba62d6b2e9751
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 59%

---

# Detalhamento de dimensões no Espaço de trabalho

Você pode detalhar seus dados de inúmeras maneiras e de acordo com suas necessidades específicas, criando consultas com o uso de métricas, dimensões, segmentos, linhas do tempo e outros valores de detalhamento de análise relevantes.

1. Em uma [Tabela de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md), no menu de contexto de uma ou mais linhas selecionadas, selecione **[!UICONTROL Detalhamento]** ![DivisaDireita](/help/assets/icons/ChevronRight.svg).

   ![Resultado da Etapa mostrando Criar alerta a partir da seleção selecionada.](assets/breakdown.png)

1. No submenu, selecione **[!UICONTROL Dimensões]**, **[!UICONTROL Métricas]**, **[!UICONTROL Segmentos]** ou **[!UICONTROL Intervalos de datas]** e selecione um item. Ou simplesmente procure por um componente no campo **[!UICONTROL *Pesquisa *]**.

Você pode analisar métricas por itens de dimensão ou segmentos de público-alvo em todos os períodos selecionados. É possível especificar ainda mais para um nível mais granular.

>[!NOTE]
>
>O número de detalhamentos exibidos na tabela é limitado a 200. Esse limite aumenta para exportar detalhamentos.

## Detalhamento por posição

Por padrão, os detalhamentos são corrigidos em itens de linha estáticos. Por exemplo, imagine que você detalhou os três principais itens de dimensão de página (Página inicial, Resultados de pesquisa, Check-out) por canal de marketing. Você sai do projeto e retorna duas semanas depois. Ao abrir o projeto novamente, as 3 principais páginas foram alteradas e, agora, a Página inicial, os Resultados da pesquisa e o Check-out são as 4 a 6 principais páginas. Por padrão, os detalhamentos do Canal de marketing ainda aparecem em Página inicial, Resultados de pesquisa e Check-out, mesmo que agora estejam nas linhas 4 a 6.

Por outro lado, o **Detalhamento por posição** sempre detalha os três itens principais, independentemente de quais sejam esses itens. Voltando ao exemplo, ao reabrir o projeto, os detalhamentos do canal de marketing são vinculados às três principais páginas da tabela. E não para Página inicial, Resultados de pesquisa e Check-out, que agora estão nas linhas 4 a 6. Consulte [Configurações de linha](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md) para saber como definir esta configuração.



## Aplicar modelos de atribuição a detalhamentos

Qualquer detalhamento em uma tabela também pode ter qualquer modelo de atribuição aplicado a ela. Esse modelo de atribuição pode ser o mesmo ou diferente da coluna pai. Por exemplo, você pode analisar Pedidos lineares em sua dimensão de Canais de marketing mas deseja aplicar Pedidos de forma de U aos códigos de rastreamento específicos em um Canal. Para editar o modelo de atribuição aplicado a um detalhamento, passe o mouse sobre o modelo de detalhamento e selecione **[!UICONTROL Editar]**.

![Comparação de atribuição de pedido mostrando as configurações de Detalhamento](assets/breakdown-attribution.png)

Este é o comportamento esperado ao aplicar modelos de atribuição a detalhamentos ou editá-los:

* Se você aplicar uma atribuição quando nenhuma outra atribuição existir, ela será aplicada a toda a árvore de colunas.

* Se você adicionar um detalhamento depois que uma atribuição for aplicada, ele usará o padrão para o detalhamento que foi adicionado (se essa dimensão tiver um padrão). Caso contrário, ele usará o detalhamento da coluna pai. Algumas dimensões têm uma alocação padrão. Por exemplo, as dimensões de Tempo e Referenciador usam o mesmo contato. A dimensão de Produto usa o último contato. Outras dimensões não têm um padrão e usarão a alocação de coluna master.

* Se já houver atribuições na árvore de colunas, alterar a atribuição afetará somente a que você estiver editando.

>[!BEGINSHADEBOX]

Assista a ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimension no Analysis Workspace](https://video.tv.adobe.com/v/30776?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Detalhamentos do Dimension](https://video.tv.adobe.com/v/30775?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adicionando dimensões e métricas](https://video.tv.adobe.com/v/33856?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Trabalhando com dimensões em uma Tabela de Forma Livre](https://video.tv.adobe.com/v/328535?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [detalhamento do Dimension por posição](https://video.tv.adobe.com/v/30774?captions=por_br){target="_blank"} para ver um vídeo de demonstração.


>[!ENDSHADEBOX]



<!--
# Break down dimensions

Break down dimensions and dimension items in Analysis Workspace.

Break down your data in unlimited ways for your specific needs; build queries using relevant metrics, dimensions, segments, time lines, and other analysis breakdown values.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table.
1. In the data table, right-click a line item and select **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Step Result](assets/fa_data_table_actions.png)

   You can break down metrics by dimension items or audience segments across selected time periods. You can also drill down further to a more granular level.

   >[!NOTE]
   >
   >The number of breakdowns to show in the table is limited to 200. This limit will increase for exporting breakdowns.

## Apply attribution models to breakdowns

Any breakdown within a table can also have any attribution model applied to it. This attribution model can be the same or different from the parent column. For example, you can analyze linear Orders on your Marketing Channels dimension but apply U-Shaped Orders to the specific tracking codes within a Channel. To edit the attribution model applied to a breakdown, hover over the breakdown model and click **[!UICONTROL Edit]**:

![Breakdown settings](assets/breakdown_settings.png)

This is the expected behavior when applying attribution models to breakdowns or editing them:

* If you apply an attribution when no other attributions exist, then the attribution applies to the entire column tree.

* If you add a breakdown after an attribution has been applied, it will use the default for the given breakdown that was added, if that dimension has a default. Otherwise it will use the breakdown from the parent column. Some dimensions have a default allocation.  For example, [!UICONTROL Time] dimensions and [!UICONTROL Referrer] use [!UICONTROL Same Touch]. The [!UICONTROL Product] dimension uses [!UICONTROL Last Touch]. Other dimensions don't have a default, and will use the parent column allocation.

* If there are already attributions in the column tree, changing the attribution only impacts the one you are editing.

## Videos


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding dimensions and metrics to your project in Analysis Workspace](https://video.tv.adobe.com/v/33856?quality=12&learn=on&captions=por_br){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Working with dimensions in a Freeform Table](https://video.tv.adobe.com/v/328535?quality=12&learn=on&captions=por_br){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [dimension breakdowns by position](https://video.tv.adobe.com/v/30774?quality=12&learn=on&captions=por_br){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


-->