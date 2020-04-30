---
description: 'Você pode usar as dimensões do AAM Audience por todo o Analytics. Os segmentos integrados são as novas dimensões do Analytics, chamadas IDs de públicos-alvo e Nomes de públicos-alvo, e podem se usadas da mesma maneira que qualquer dimensão que o Analytics coleta. Em Feeds de dados, as IDs de públicos-alvo são armazenadas na coluna “mc_audiences”. Essas dimensões não estão disponíveis no Data Workbench ou na Transmissão em tempo real. São exemplos de como as dimensões de Públicos-alvo podem ser aproveitadas '
solution: Experience Cloud
title: Usar os dados de público-alvo no Analytics
uuid: 203925fb-f070-441c-813a-43099cb9b2b9
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Usar os dados de público-alvo no Analytics

Você pode usar as dimensões do AAM Audience por todo o Analytics. Os segmentos integrados são as novas dimensões do Analytics, chamadas IDs de públicos-alvo e Nomes de públicos-alvo, e podem se usadas da mesma maneira que qualquer dimensão que o Analytics coleta. Em Feeds de dados, as IDs de públicos-alvo são armazenadas na coluna “mc_audiences”. Essas dimensões não estão disponíveis no Data Workbench ou na Transmissão em tempo real. São exemplos de como as dimensões de Públicos-alvo podem ser aproveitadas:

## Analysis Workspace {#section_C70837499BEA4DED885B3486C9E02C68}

Na Analysis Workspace, os segmentos do AAM aparecem como duas dimensões.

1. Vá para **[!UICONTROL Workspace]**.
1. Na lista de **[!UICONTROL Dimensions]**, selecione as dimensões **[!UICONTROL Audience ID]** ou **[!UICONTROL Audience Name]**. Nome é uma classificação amigável da ID.

   ![](assets/aw-mcaudiences.png)

## Comparação de segmentos {#section_E72B80B6470C42D4B9B19BE90E6070A2}

A [Comparação de segmentos](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) encontra as diferenças estatísticas mais relevantes entre dois segmentos. Dados de Públicos-alvo podem ser usados na Comparação de segmentos de duas maneiras: 1) como os 2 segmentos sendo comparados, e 2) como itens na tabela “Itens de dimensão principais”.

1. Go to **[!UICONTROL Workspace]** and select the **[!UICONTROL Segment Comparison]** panel from the left rail.

1. Procure [!UICONTROL Audiences Name] no **[!UICONTROL Component]** menu.

1. Open [!UICONTROL Audiences Name]so that the related dimension items appear.
1. Arraste os públicos-alvo que você deseja comparar para o construtor de Comparação de segmentos.
1. (Opcional): é possível arrastar também outros itens de dimensão ou segmentos; até 2 podem ser comparados.
1. Clique em **[!UICONTROL Build]**.

   As dimensões IDs e Nomes de públicos-alvo serão exibidas automaticamente na tabela “Itens de dimensão principais”, por serem dados adicionais do perfil referentes aos dois segmentos sendo comparados.

   ![](assets/aud-segcompare.png)

## Jornada do cliente (Fluxo) na Analysis Workspace {#section_FC30E5795C9D4539838E30FE11FAEA6E}

Dados de segmento do AAM são passados para o Analytics em uma base ocorrência-por-ocorrência, e representam a associação de público-alvo de um visitante naquele período específico. Ou seja, um visitante pode se encaixar em um segmento (ex. “Percepção”) e depois se classificar para um segmento mais qualificado (ex. “Consideração“). Use [Fluxo](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) na Analysis Workspace para visualizar a jornada feita por um cliente entre públicos-alvo.

1. Go to **[!UICONTROL Workspace]** and select the **[!UICONTROL Flow]** visualization from the left rail.

1. Drag the [!UICONTROL Audience Name] dimension into the Flow builder.
1. Clique em **[!UICONTROL Build]**.
1. (Opcional): arraste qualquer outra dimensão para a visualização de Fluxo para criar um [Fluxo interdimensional](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/multi-dimensional-flow.html).

![](assets/flow-aamaudiences.png)

Públicos-alvo também podem ser usados em [visualizações de Fallout](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html).

## Visualização de Venn na Analysis Workspace  {#section_E78AB764FB5047148B51DC1526B0DF89}

[Visualizações de Venn](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/venn.html) mostram a sobreposição entre até 3 segmentos.

1. Go to **[!UICONTROL Workspace]** and select the **[!UICONTROL Venn]** visualization from the left rail.

1. Procure [!UICONTROL Audience Name] no menu de componentes.
1. Open [!UICONTROL Audience Name] so that the related dimension items appear.
1. Arraste os públicos-alvo que você deseja comparar para o construtor de Venn.
1. (Opcional): você pode arrastar também outros itens de dimensão ou segmentos; até 3 podem ser comparados.
1. Clique em **[!UICONTROL Build]**.

![](assets/venn-viz.png)

## Construtor de segmentos {#section_2AA81852A1404AB894472CA8959461B6}

É possível incorporar as dimensões de Públicos-alvo no [Construtor de segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) do Analytics, junto às informações de comportamento coletadas pelo Analytics.

1. Vá para  **[!UICONTROL Components]** > **[!UICONTROL Segments]** .
1. Click **[!UICONTROL Add]** to create a new segment.
1. After naming the segment, drag the [!UICONTROL Audience Name] dimension into the Definitions panel.
1. (Opcional): adicione outros critérios ao segmento.
1. Salve o segmento.

   ![](assets/aud-segbuilder.png)

## Relatórios e análises e Construtor de relatórios  {#section_04E8FD30F73344D7937AD3C6CD19E34A}

1. Para visualização do relatório do Analytics, acesse **[!UICONTROL Reports]** > **[!UICONTROL Visitor Profile]** > **[!UICONTROL Audience ID Reports]** .
1. Nessa pasta, é possível acessar as dimensões ID de público-alvo e Nome de público-alvo.

   ![](assets/mc-audiences.png)

