---
description: Há duas formas de utilizar as métricas no Analysis Workspace.
title: Métricas no Analysis Workspace
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: e0a10540bdfbd9fa3694ff3c7a8585eeb87eaad8
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 24%

---

# Métricas

As métricas permitem quantificar os pontos de dados no Analysis Workspace. Elas são usadas com mais frequência como colunas em uma visualização e vinculadas a dimensões.

O Adobe oferece vários tipos de métricas para uso no Analysis Workspace:

* **Métricas padrão**: a maioria das métricas usadas em projetos é padrão. Os exemplos incluem [Exibições de página](/help/components/metrics/page-views.md), [Receita](/help/components/metrics/revenue.md)ou [Eventos personalizados](/help/components/metrics/custom-events.md). Consulte [Visão geral das métricas](/help/components/metrics/overview.md) no guia do usuário Componentes para obter mais informações.

   ![Métrica padrão](assets/standard-metric.png)

* **Métricas calculadas**: métricas definidas pelo usuário baseadas em métricas padrão, números estáticos ou funções algorítmicas. As métricas calculadas definidas pelo usuário mostram um ícone de calculadora na lista de componentes disponíveis. Consulte [Visão geral das métricas calculadas](/help/components/c-calcmetrics/cm-overview.md) no guia do usuário Componentes para obter mais informações.

   ![Métrica calculada](assets/calculated-metric.png)

* **Modelos de métrica calculada**: métricas definidas por Adobe que se comportam de forma semelhante às métricas calculadas. Você pode usá-los como estão nos projetos do Workspace ou salvar uma cópia para personalizar a lógica. Os modelos de métrica calculada mostram um ícone de Adobe na lista de componentes disponíveis.

   ![Modelo de métrica calculada](assets/calculated-metric-template.png)

As métricas são flexíveis em seu uso no Analysis Workspace. Arraste uma métrica para uma Tabela de forma livre vazia para ver a tendência da métrica no período do projeto. Você também pode arrastar uma métrica quando uma dimensão estiver presente para ver essa métrica em comparação com cada item de dimensão. Arrastar uma métrica para cima de um cabeçalho de métrica existente a substitui e arrastar uma métrica ao lado de um cabeçalho permite ver ambas as métricas lado a lado.

>[!VIDEO](https://video.tv.adobe.com/v/40817/?quality=12)

## Métricas calculadas 

Métricas calculadas permitem ver facilmente como as métricas se relacionam entre si usando operadores simples ou funções estatísticas. Há várias maneiras de criar métricas calculadas:

* Clique no ícone de adição ao lado do cabeçalho Métricas na lista de componentes à esquerda.
* Navegue até **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]** > **[!UICONTROL Adicionar]**.
* Clique com o botão direito em um cabeçalho de coluna > **[!UICONTROL Criar métrica a partir da seleção]** quando uma ou mais células de coluna de cabeçalho são selecionadas. Essa opção cria automaticamente uma métrica calculada para você sem precisar usar o Construtor de regras de métrica calculada.

[Métricas calculadas: métricas sem implementação](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=pt-BR) (3:42)

## Comparar métricas com diferentes modelos de atribuição

Se você quiser comparar um modelo com outro de maneira fácil e rápida, clique com o botão direito em uma métrica e selecione **[!UICONTROL Comparar modelos de atribuição]**:

![Comparar atribuição](assets/compare-attribution.png)

Esse atalho permite comparar de forma rápida e fácil um modelo de atribuição com outro, sem arrastar uma métrica e configurá-la duas vezes.

## Usar a função [!UICONTROL média cumulativa] para aplicar a suavização de métricas

Veja um vídeo sobre este tópico:

>[!VIDEO](https://video.tv.adobe.com/v/27068/?quality=12)
