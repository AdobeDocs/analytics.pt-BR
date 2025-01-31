---
description: Um histograma é um novo tipo de visualização no Analysis Workspace.
title: Histograma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: b2e91c9981b328aa34e03dcd3b713438732ea6b1
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 34%

---

# Histograma {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histograma"
>abstract="Crie uma visualização de histograma para representar a distribuição de dados numéricos em grupos de intervalos."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta a visualização do Histograma no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte o [Histograma](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/histogram) da_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** versão deste artigo._

>[!ENDSHADEBOX]


A visualização do ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]** é semelhante a uma visualização de [!UICONTROL Barra], mas agrupa números em intervalos (compartimentos). O Analytics automatiza o agrupamento de números em intervalos, mas você pode alterar as configurações em [Configurações avançadas](#advanced-settings).

## Usar

Para criar um histograma:

1. Adicionar uma visualização de ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]**. Consulte [Adicionar uma visualização a um painel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Arraste uma métrica da lista de componentes **[!UICONTROL Métricas]** ou selecione uma métrica do menu suspenso [!UICONTROL *Adicionar uma métrica*].
1. (opcional) Selecione **[!UICONTROL Mostrar configurações avançadas]**. Consulte [Configurações avançadas](#advanced-settings).
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
| **[!UICONTROL Compartimento inicial]** | Determina o grupo inicial do histograma. O valor padrão é “1”. Você pode definir números iniciais de 0 a infinito (nenhum número negativo). |
| **[!UICONTROL Compartimentos de métrica]** | Permite aumentar/diminuir o número de intervalos de dados (compartimentos). O número máximo de compartimentos é 50. |
| **[!UICONTROL Tamanho do bucket de métrica]** | Permite definir o tamanho de cada grupo. Por exemplo, você pode alterar o tamanho do grupo de uma exibição de página para duas exibições de página. |
| **[!UICONTROL Método de contagem]** | Selecione de **[!UICONTROL Pessoa]**, **[!UICONTROL Sessão]** ou **[!UICONTROL Evento]**. Por exemplo, exibições de página por sessão, por pessoa ou por evento. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemplos**:

| Período inicial | Classificações de métrica | Tamanho do bucket de métrica | Resultado |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histograma, bloco inicial 1, compartimentos de métrica 5, tamanho do compartimento de métrica 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histograma, classificação inicial 0, classificações de métrica 3, tamanho de classificação de métrica 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>[Usando histogramas para identificar valores de dados inesperados](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

