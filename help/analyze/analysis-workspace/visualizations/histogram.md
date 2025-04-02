---
description: Um histograma é um novo tipo de visualização no Analysis Workspace.
title: Histograma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: b2e91c9981b328aa34e03dcd3b713438732ea6b1
workflow-type: ht
source-wordcount: '338'
ht-degree: 100%

---

# Histograma {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histograma"
>abstract="Crie uma visualização de histograma para representar a distribuição de dados numéricos em grupos de intervalos."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo é sobre a visualização de histograma no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte [Histograma](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/visualizations/histogram) para ver a versão do_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** deste artigo._

>[!ENDSHADEBOX]


A visualização de ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL histograma]** é semelhante a uma visualização de [!UICONTROL barras], mas agrupa os números em intervalos (compartimentos). O Analytics automatiza o agrupamento de números em intervalos, mas é possível alterar as configurações em [Configurações avançadas](#advanced-settings).

## Usar

Para criar um histograma:

1. Adicione uma visualização de ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL histograma]**. Consulte [Adicionar uma visualização a um painel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Arraste uma métrica da lista de componentes de **[!UICONTROL Métricas]** ou selecione uma métrica do menu suspenso [!UICONTROL *Adicionar uma métrica*].
1. (Opcional) Selecione **[!UICONTROL Mostrar configurações avançadas]**. Consulte [Configurações avançadas](#advanced-settings).
1. Selecione **[!UICONTROL Criar]**.

>[!NOTE]
>
>Os histogramas são compatíveis apenas com métricas padrão, não calculadas.

No exemplo abaixo, um histograma é usado para agrupar sessões de número de pessoas. O histograma mostra que a maioria das pessoas tem entre 16 e 21 sessões para o intervalo de datas selecionado.

![](assets/histogram.png)

## Configurações avançadas

Como parte da visualização, há configurações específicas do histograma disponíveis.

| Configurações do histograma | Descrição |
|---|---|
| **[!UICONTROL Compartimento inicial]** | Determina o grupo inicial do histograma. O valor padrão é “1”. Você pode definir números iniciais de 0 a infinito (nenhum número negativo). |
| **[!UICONTROL Compartimentos de métricas]** | Permite aumentar ou diminuir o número de intervalos de dados (compartimentos). O número máximo de compartimentos é 50. |
| **[!UICONTROL Tamanho do compartimento de métricas]** | Permite definir o tamanho de cada grupo. Por exemplo, você pode alterar o tamanho do grupo de uma exibição de página para duas exibições de página. |
| **[!UICONTROL Método de contagem]** | Selecione entre **[!UICONTROL Pessoa]**, **[!UICONTROL Sessão]** ou **[!UICONTROL Evento]**. Por exemplo, exibições de página por sessão, por pessoa ou por evento.  |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemplos**:

| Compartimento inicial | Compartimentos de métricas | Tamanho do compartimento de métricas | Resultado |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histograma, compartimento inicial 1, compartimentos de métricas 5, tamanho do compartimento de métricas 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histograma, compartimento inicial 0, compartimentos de métricas 3, tamanho do compartimento de métricas 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>[Uso de histogramas para identificar valores de dados inesperados](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168?profile.language=pt)

