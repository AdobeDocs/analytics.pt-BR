---
description: Lista de limitações conhecidas do Adobe Analysis Workspace e dos componentes relacionados a ele
title: Limitações conhecidas do Analysis Workspace
translation-type: tm+mt
source-git-commit: 06d2e64fc72c911828f089de5c487117251e060e

---


# Limitações conhecidas do Analysis Workspace

Veja a seguir uma lista de limitações conhecidas do Analysis Workspace e seus componentes relacionados:

## Tabelas

* Colunas de comparação de datas não podem ser adicionadas quando intervalos de datas ou métricas são usados como linhas de uma tabela.
* A opção Criar métrica a partir da seleção é desativada quando os segmentos são usados como linhas de uma tabela. Além disso, a opção Criar métrica a partir da seleção não deve ser aplicada a colunas alinhadas por data.
* A formatação condicional para linhas de detalhamento não pode usar intervalos personalizados.
* O total de linhas da tabela não pode incluir a tendência quando a configuração Calcular totais somando os valores das linhas (normalmente usada com itens de linhas estáticas) tiver sido usada.
* [!UICONTROL Contribution Analysis] pode ser executado [!UICONTROL daily] somente _na_ granularidade. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualizações

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]: Dimensões de entrada/saída, por exemplo, [!UICONTROL Entry page], não pode ser usado em Fluxo.
* [!UICONTROL Cohort]: Não é possível usar números inteiros como critérios de coorte.

## Painéis

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Componentes > Segmentos

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). Por exemplo, Endereço IP.

## Componentes > Métricas calculadas

* As Métricas calculadas não podem ser usadas em determinadas visualizações. Consulte o tópico “Visualizações” acima.
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). Por exemplo, [!UICONTROL IP Address].

## Componentes > Intervalos de datas

* Intervalos de datas personalizados não são compatíveis [!UICONTROL This day last year], [!UICONTROL This day last month]etc.

## Componentes > Conjuntos de relatórios virtuais

* Quando o processamento de tempo do relatório está ativado, determinados componentes não são compatíveis. Para obter uma lista completa, consulte [Processamento de tempo do relatório](/help/components/vrs/vrs-report-time-processing.md).

## Componentes > Configurações de relatório

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. A Analysis Workspace usa somente as [!UICONTROL Language/Currency/Encoding] configurações na parte inferior: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding]e [!UICONTROL CSV Separator Character].

## Attribution IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. Para obter uma lista completa, consulte as Perguntas frequentes sobre [Attribution IQ](c-panels/attribution/attribution-faq.md).
