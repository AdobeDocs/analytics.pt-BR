---
description: Um histograma é um novo tipo de visualização no Analysis Workspace.
title: Histograma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Histograma

Um histograma é semelhante a um gráfico de barras, mas agrupa os números em intervalos (grupos). O Analytics automatiza o agrupamento de números em intervalos, mas você pode alterar as configurações em [Configurações avançadas](#section_09D774C584864D4CA6B5672DC2927477).

## Criar um histograma {#section_74647707CC984A1CB6D3097F43A30B45}

Para criar um histograma:

1. Click **[!UICONTROL Visualizations]** in the left rail.
1. Drag **[!UICONTROL Histogram]** to the panel.
1. Choose a Metric to drag to the Histogram visualization and click **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE] Os histogramas são compatíveis apenas com métricas padrão, não calculadas.

Aqui, utilizamos a Métrica de exibições de página por visitantes exclusivos. O primeiro grupo (à esquerda) corresponde a uma exibição de página por visitante exclusivo, o segundo grupo, a duas exibições de página, etc.

![](assets/histogram2.png)

## Configurações avançadas {#section_09D774C584864D4CA6B5672DC2927477}

Para ajustar as configurações do histograma, clique no ícone de Configurações (“engrenagem”) no canto superior direito. Estas são as configurações que você pode modificar:

| Configurações do histograma | O que faz |
|---|---|
| Grupo inicial | Determina o grupo inicial do histograma. O valor padrão é “1”. Você pode definir números iniciais de 0 a infinito (nenhum número negativo). |
| Grupos de métricas | Permite aumentar/diminuir o número de intervalos de dados (grupos). O número máximo de grupos é 50. |
| Tamanho do grupo de métricas | Permite definir o tamanho de cada grupo. Por exemplo, você pode alterar o tamanho do grupo de uma exibição de página para duas exibições de página. |
| Método de contagem | Lets you choose among [Visitor](/help/components/c-variables/c-metrics/visitors.md), [Visit](/help/components/c-variables/c-metrics/metrics-visit.md), or [Hit Type](/help/components/c-variables/dimensionslist/report-hit-type.md). Por exemplo, exibições de página por visita, por visitante ou por ocorrência. Para ocorrências, “Ocorrências” é usada como a métrica do eixo “y” na tabela de forma livre. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemplos**:

* Grupo inicial: 1; Grupos de métricas: 5; Tamanho do grupo de métricas: 2 resultará neste histograma: 1-2, 3-4, 5-6, 7-8, 9-10.
* Grupo inicial: 0; Grupos de métricas: 3; Tamanho do grupo de métricas: 5 resultará neste histograma: 0-4, 5-9, 10-14.

## Exibir e editar os dados do histograma {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

To view or change the data source for the histogram chart, click the dot next to the Histogram header to go to **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

Os segmentos pré-construídos exibidos na tabela são segmentos internos e não serão exibidos no seletor de segmentos. Click the &quot;i&quot; icon next to the segment name, then click **[!UICONTROL Make public]** to make the segment public.

![](assets/prebuilt_segments.png)

Para explorar mais formas de gerenciar tabelas de dados de forma livre e outras visualizações, como detalhamento de dados, clique [aqui](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html).
