---
description: Um histograma é um novo tipo de visualização no Analysis Workspace.
title: Histograma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 90%

---

# Histograma {#histogram}

arkdownlint-disable MD034 —>

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histograma"
>abstract="Crie uma visualização de histograma para representar a distribuição de dados numéricos em grupos de intervalos."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta a visualização do Histograma no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte o [Histograma](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/histogram) da_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** versão deste artigo._

>[!ENDSHADEBOX]


Um histograma é semelhante a um gráfico de barras, mas agrupa os números em intervalos (grupos). O Analytics automatiza o agrupamento de números em intervalos, mas você pode alterar as configurações em [Configurações avançadas](#section_09D774C584864D4CA6B5672DC2927477).

Veja um vídeo sobre como usar histogramas:

>[!VIDEO](https://video.tv.adobe.com/v/23725/?quality=12)

## Criar um histograma {#section_74647707CC984A1CB6D3097F43A30B45}

Para criar um histograma:

1. Clique em **[!UICONTROL Visualizações]** no painel à esquerda.
1. Arraste **[!UICONTROL Histograma]** ao painel.
1. Escolha uma Métrica para arrastar à visualização do Histograma e clique em **[!UICONTROL Criar]**.

![](assets/histogram.png)

>[!NOTE]
>
>Os histogramas são compatíveis apenas com métricas padrão, não calculadas.

Aqui, utilizamos a Métrica de exibições de página por visitante únicos. O primeiro grupo (à esquerda) corresponde a uma exibição de página por visitante único, o segundo grupo, a duas exibições de página, etc.

![](assets/histogram2.png)

## Configurações avançadas {#section_09D774C584864D4CA6B5672DC2927477}

Para ajustar as configurações do histograma, clique no ícone de Configurações (“engrenagem”) no canto superior direito. Estas são as configurações que você pode modificar:

| Configurações do histograma | O que faz |
|---|---|
| Grupo inicial | Determina o grupo inicial do histograma. O valor padrão é “1”. Você pode definir números iniciais de 0 a infinito (nenhum número negativo). |
| Grupos de métricas | Permite aumentar/diminuir o número de intervalos de dados (compartimentos). O número máximo de compartimentos é 50. |
| Tamanho do grupo de métricas | Permite definir o tamanho de cada grupo. Por exemplo, você pode alterar o tamanho do grupo de uma exibição de página para duas exibições de página. |
| Método de contagem | Permite escolher entre [Visitante](/help/components/metrics/unique-visitors.md), [Visita](/help/components/metrics/visits.md) ou [Tipo de ocorrência](/help/components/dimensions/hit-type.md). Por exemplo, exibições de página por visita, por visitante ou por ocorrência. Para ocorrências, “Ocorrências” é usada como a métrica do eixo “y” na tabela de forma livre. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemplos**:

* Grupo inicial: 1; Grupos de métricas: 5; Tamanho do grupo de métricas: 2 resultará neste histograma: 1-2, 3-4, 5-6, 7-8, 9-10.
* Grupo inicial: 0; Grupos de métricas: 3; Tamanho do grupo de métricas: 5 resultará neste histograma: 0-4, 5-9, 10-14.

## Exibir e editar os dados do histograma {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Para exibir ou alterar a fonte de dados do gráfico de histograma, clique no ponto ao lado do cabeçalho do Histograma para acessar **[!UICONTROL Configurações da fonte de dados]** > **[!UICONTROL Mostrar fonte de dados]**.

![](assets/manage-data-source.png)

Os segmentos pré-construídos exibidos na tabela são segmentos internos e não serão exibidos no seletor de segmentos. Clique no ícone “i” ao lado do nome do segmento e em **[!UICONTROL Tornar público]** para tornar o segmento público.

![](assets/prebuilt_segments.png)

Para explorar mais formas de gerenciar tabelas de dados de forma livre e outras visualizações, como detalhamento de dados, clique [aqui](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=pt-BR).
