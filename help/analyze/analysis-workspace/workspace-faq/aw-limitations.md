---
description: Saiba mais sobre as limitações conhecidas do Adobe Analysis Workspace e seus componentes relacionados
title: Limitações Conhecidas Do Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
source-git-commit: d37fa0aff0b1bbe196b943bc26e86b1e79936184
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 98%

---

# Limitações conhecidas do Analysis Workspace

Veja a seguir uma lista de limitações conhecidas do Analysis Workspace e seus componentes relacionados:

## Tabelas

* Colunas de comparação de datas não podem ser adicionadas quando intervalos de datas ou métricas são usados como linhas de uma tabela.
* A opção Criar métrica a partir da seleção é desativada quando os segmentos são usados como linhas de uma tabela. Além disso, a opção Criar métrica a partir da seleção não deve ser aplicada a colunas alinhadas por data.
* A formatação condicional para linhas de detalhamento não pode usar intervalos personalizados.
* O total de linhas da tabela não pode incluir a tendência quando a configuração Calcular totais somando os valores das linhas (normalmente usada com itens de linhas estáticas) tiver sido usada.

## Visualizações

* Visualizações que aproveitam segmentos, como [!UICONTROL Fallout], [!UICONTROL Fluxo], [!UICONTROL Coorte] e [!UICONTROL Histograma], não podem aceitar métricas calculadas como entradas.
* [!UICONTROL Fluxo]: as dimensões de entrada/saída, por exemplo, [!UICONTROL Página de entrada], não podem ser usadas em Fluxo.
* [!UICONTROL Coorte]: não é possível usar números não inteiros como critérios de coorte.

## Segmentos

* Certas métricas e dimensões não podem ser segmentadas, como [!UICONTROL Eventos], [!UICONTROL Pessoas] etc.
* Segmentos ad hoc criados na [zona de destino do painel](/help/analyze/analysis-workspace/c-panels/panels.md) são um tipo de segmento rápido. Eles não aparecem no painel esquerdo do espaço de trabalho ou no gerenciador de segmentos, a menos que sejam tornados públicos. Para obter mais informações, consulte [Segmentos rápidos](/help/components/segmentation/segmentation-workflow/seg-quick.md).

## Métricas calculadas 

* As métricas calculadas não podem ser usadas em determinadas visualizações. Consulte [Visualizações](#visualizations).
* Métricas calculadas não podem ser usadas no painel [!UICONTROL Atribuição], já que podem incluir modelos de atribuição separados.
* Certos componentes e operadores não estarão disponíveis se uma métrica calculada for criada do espaço de trabalho (em vez de ser criada a partir de [!UICONTROL Componentes > Segmentos]). Por exemplo, [!UICONTROL Endereço IP].

## Intervalos de datas

* Os intervalos de datas personalizados não são compatíveis com [!UICONTROL Este dia no ano passado], [!UICONTROL Este dia no mês passado] etc.


## Configurações de relatório

* Algumas das configurações na página [!UICONTROL Configurações do relatório] não se aplicam. O Analysis Workspace usa somente as configurações [!UICONTROL Idioma/Moeda/Codificação] na parte inferior: [!UICONTROL Separador de milhares], [!UICONTROL Codificação do relatório agendado] e [!UICONTROL Caractere separador CSV].



<!--
# Known limitations in Analysis Workspace 

Here is a list of known limitations in Analysis Workspace and its related components:

## Tables

* Date comparison columns cannot be added when either date ranges or metrics are used as rows of a table.
* Create metric from selection is disabled when segments are used as rows of a table. Additionally, Create metric from selection should not be applied to date-aligned columns.
* Conditional formatting for breakdown rows cannot use custom ranges.
* Table total rows cannot be trended when Calculate totals by summing the row values setting is applied (typically used with Static row items).
* [!UICONTROL Contribution Analysis] can be run at the [!UICONTROL daily] granularity _only_. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualizations

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]: Entry/Exit dimensions, e.g. [!UICONTROL Entry page], cannot be used in Flow.
* [!UICONTROL Cohort]: Non-integers cannot be used as Cohort criteria.

## Panels

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Components > Segments

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Adhoc segments created in the [panel dropzone](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=pt-BR) are a type of quick filter. They do not appear in the left rail of Workspace or the Segment component manager unless they are made public. For more information, see [Quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

## Components > Calculated Metrics

* Calculated metrics cannot be used in certain visualizations. See 'Visualizations' above.
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). For example, [!UICONTROL IP Address].

## Components > Date Ranges

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## Components > Virtual Reports Suites

* When report time processing is enabled, certain components are not supported. For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## Components > All components > Report settings

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## Attribution

* A subset of metrics is not supported in [!UICONTROL Attribution]. For a full list, see the [Attribution FAQ](/help/analyze/analysis-workspace/attribution/faq.md).
-->
