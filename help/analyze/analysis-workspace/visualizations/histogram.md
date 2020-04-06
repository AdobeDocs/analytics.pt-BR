---
description: Um histograma é um novo tipo de visualização no Analysis Workspace.
title: Histograma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Histograma

Um histograma é semelhante a um gráfico de barras, mas agrupa números em intervalos (grupos). O Analytics automatiza a &quot;segmentação&quot; de números em intervalos, mas é possível alterar as configurações em Configurações [](#section_09D774C584864D4CA6B5672DC2927477)avançadas.

## Criar um histograma {#section_74647707CC984A1CB6D3097F43A30B45}

Para criar um histograma:

1. Click **[!UICONTROL Visualizations]** in the left rail.
1. Drag **[!UICONTROL Histogram]** to the panel.
1. Choose a Metric to drag to the Histogram visualization and click **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE] Os histogramas são compatíveis apenas com métricas padrão, não calculadas.

Aqui usamos a Métrica de Visualizações de página por Visitantes únicos. O primeiro grupo (à esquerda) corresponde a uma visualização de página por visitante exclusivo, o segundo grupo corresponde a duas visualizações de página, etc.

![](assets/histogram2.png)

## Configurações avançadas {#section_09D774C584864D4CA6B5672DC2927477}

Para ajustar as configurações do histograma, clique no ícone Configurações (&quot;engrenagem&quot;) no canto superior direito. Estas são as configurações que você pode modificar:

| Configurações do histograma | O que faz |
|---|---|
| Bucket inicial | Determina com qual grupo os start do histograma estão incluídos. &quot;1&quot; é o padrão. É possível definir números iniciais de 0 a infinito (sem números negativos). |
| Grupos de métricas | Permite aumentar/diminuir o número de intervalos de dados (grupos). O número máximo de compartimentos é 50. |
| Tamanho do grupo de métricas | Permite definir o tamanho de cada bucket. Por exemplo, você pode alterar o tamanho do grupo de 1 visualização de página para 2 visualizações de página. |
| Método de contagem | Permite escolher entre [Visitante](https://marketing.adobe.com/resources/help/pt_BR/reference/visitors.html), [Visita](https://marketing.adobe.com/resources/help/pt_BR/reference/metrics_visit.html)ou [Ocorrência](https://marketing.adobe.com/resources/help/pt_BR/reference/hit.html). Por exemplo, visualizações de página por visita ou visualizações de página por visitante ou visualizações de página por ocorrência. Para ocorrências, “Ocorrências” é usada como a métrica do eixo “y” na tabela de forma livre. |

**Exemplos**:

* Grupo inicial: 1; Grupos de métricas: 5; Tamanho do grupo de métricas: 2 resultará neste histograma: 1-2, 3-4, 5-6, 7-8, 9-10.
* Grupo inicial: 0; Grupos de métricas: 3; Tamanho do grupo de métricas: 5 resultará neste histograma: 0-4, 5-9, 10-14

## Exibir e editar os dados do histograma {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

To view or change the data source for the histogram chart, click the dot next to the Histogram header to go to **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

Os segmentos pré-construídos exibidos na tabela são segmentos internos e não serão exibidos no seletor de segmentos. Click the &quot;i&quot; icon next to the segment name, then click **[!UICONTROL Make public]** to make the segment public.

![](assets/prebuilt_segments.png)

Para explorar mais formas de gerenciar tabelas de dados de forma livre e outras visualizações, como detalhamento de dados, clique [aqui](https://marketing.adobe.com/resources/help/pt_BR/analytics/analysis-workspace/freeform-analysis-visualizations.html).
