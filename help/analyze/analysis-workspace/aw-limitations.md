---
description: 'null'
seo-description: 'null'
seo-title: Limitações do Espaço de trabalho, Limitações conhecidas na Analysis Workspace
title: Limitações conhecidas na Analysis Workspace
translation-type: tm+mt
source-git-commit: 9d6b35c7c6de6fcb49fea3b662ff8bc9044b5e29

---


# Limitações conhecidas na Analysis Workspace

Esta é uma lista de limitações conhecidas na Analysis Workspace e seus componentes relacionados:

## Tabela

* As colunas de comparação de datas não podem ser adicionadas quando intervalos de datas ou métricas são usados como linhas de uma tabela.
* A métrica Criar a partir da seleção é desativada quando os segmentos são usados como linhas de uma tabela. Além disso, a opção Criar métrica a partir da seleção não deve ser aplicada a colunas alinhadas por data.
* A formatação condicional para linhas de detalhamento não pode usar intervalos personalizados.
* As linhas totais da tabela não podem ser com tendência quando Calcular totais ao resumir a configuração de valores de linha (normalmente usada com itens de linha Estáticos).
* [!UICONTROL A Análise de contribuição] só pode ser executada [!UICONTROL com] a granularidade _diária_. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualizações

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Fluxo]: Dimensões de entrada/saída, por exemplo, página [!UICONTROL de entrada], não podem ser usadas no Fluxo.
* [!UICONTROL Coorte]: Não é possível usar números inteiros como critério de coorte.

## Painéis

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Componentes &gt; Segmentos

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). Por exemplo, Endereço IP.

## Componentes &gt; Métricas calculadas

* As métricas calculadas não podem ser usadas em algumas visualizações. Consulte'Visualizações'acima.
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). For example, [!UICONTROL IP Address].

## Componentes &gt; Intervalos de datas

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## Componentes &gt; Conjuntos de relatórios virtuais

* Quando o processamento de tempo do relatório é ativado, alguns componentes não são suportados. For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## Componentes &gt; Configurações do relatório

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## Attribution IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. For a full list, see the [Attribution IQ FAQ](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md).