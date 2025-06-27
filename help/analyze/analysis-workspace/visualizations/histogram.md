---
description: Saiba como usar um histograma, que é semelhante a um gráfico de barras, mas agrupa números em intervalos (grupos).
title: Histograma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 89%

---

# Histograma {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histograma"
>abstract="Crie uma visualização de histograma para representar a distribuição de dados numéricos em grupos de intervalos."


>[!BEGINSHADEBOX]

_Este artigo é sobre a visualização de histograma no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte [Histograma](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/visualizations/histogram) para ver a versão do_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** deste artigo._

>[!ENDSHADEBOX]


A visualização de ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL histograma]** é semelhante a uma visualização de [!UICONTROL barras], mas agrupa os números em intervalos (compartimentos). O Analytics automatiza o agrupamento de números em intervalos, mas você pode alterar as configurações em [Configurações avançadas](#advanced-settings).

## Usar

Para criar um histograma:

1. Adicionar uma visualização de ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]**. Consulte [Adicionar uma visualização a um painel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
1. Arraste uma métrica da lista de componentes **[!UICONTROL Métricas]** ou selecione uma métrica do menu suspenso [!UICONTROL *Adicionar uma métrica*].
1. Selecione **[!UICONTROL Mostrar configurações avançadas]**. Consulte [Configurações avançadas](#advanced-settings)
1. Selecione **[!UICONTROL Criar]**.

>[!NOTE]
>
>Os histogramas são compatíveis apenas com métricas padrão, não calculadas.

No exemplo abaixo, um histograma é usado para agrupar sessões para o número de pessoas. O histograma mostra que a maioria das pessoas tem entre 16 e 21 sessões para o intervalo de datas selecionado.

![](assets/histogram.png)

## Configurações avançadas

Como parte da visualização, configurações específicas do histograma estão disponíveis.

| Configurações do histograma | Descrição |
|---|---|
| **[!UICONTROL Grupo inicial]** | Determina o grupo inicial do histograma. O valor padrão é “1”. Você pode definir números iniciais de 0 a infinito (nenhum número negativo). |
| **[!UICONTROL Grupos de métricas]** | Permite aumentar/diminuir o número de intervalos de dados (compartimentos). O número máximo de compartimentos é 50. |
| **[!UICONTROL Tamanho do grupo de métricas]** | Permite definir o tamanho de cada grupo. Por exemplo, você pode alterar o tamanho do grupo de uma exibição de página para duas exibições de página. |
| **[!UICONTROL Método de contagem]** | Selecione de **[!UICONTROL Pessoa]**, **[!UICONTROL Sessão]** ou **[!UICONTROL Evento]**. Por exemplo, exibições de página por visita, por visitante ou por evento.  |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemplos**:

| Grupo inicial | Grupos de métricas | Tamanho do grupo de métricas | Resultado |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histograma, compartimento inicial 1, compartimentos de métrica 5, tamanho do compartimento de métrica 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histograma, compartimento inicial 0, compartimentos de métrica 3, tamanho do compartimento de métrica 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Configurações de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Menu de contexto de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>>[Usando histogramas para identificar valores de dados inesperados](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168?profile.language=pt)

