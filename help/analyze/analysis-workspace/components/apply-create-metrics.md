---
description: Há duas formas de utilizar as métricas no Analysis Workspace.
title: Métricas no Analysis Workspace
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 50%

---

# Métricas

As métricas permitem quantificar os pontos de dados no Analysis Workspace. Elas são usadas com mais frequência como colunas em uma visualização e são vinculadas a dimensões.

## Tipos de métricas

A Adobe oferece vários tipos de métricas para uso no Analysis Workspace:

* **Métricas padrão**: a maioria das métricas usadas em projetos é padrão. Os exemplos incluem [Visualizações de Página](/help/components/metrics/page-views.md), [Receita](/help/components/metrics/revenue.md)ou [Eventos personalizados](/help/components/metrics/custom-events.md). Consulte [Visão geral das métricas](/help/components/metrics/overview.md) no guia do usuário Componentes para obter mais informações.

  ![Métrica padrão](assets/standard-metric.png)

* **Métricas calculadas**: métricas definidas pelo usuário baseadas em métricas padrão, números estáticos ou funções algorítmicas. As métricas calculadas definidas pelo usuário mostram um ícone de calculadora na lista de componentes disponíveis. Consulte [Visão geral das métricas calculadas](/help/components/c-calcmetrics/cm-overview.md) no guia do usuário Componentes para obter mais informações.

  ![Métrica calculada](assets/calculated-metric.png)

* **Modelos de métrica calculada**: métricas definidas pela Adobe que se comportam de forma semelhante às métricas calculadas. É possível usá-los como estão nos projetos do Workspace ou salvar uma cópia para personalizar sua lógica. Os modelos de métrica calculada mostram um ícone da Adobe na lista de componentes disponíveis.

  ![Modelo de métrica calculada](assets/calculated-metric-template.png)

## Utilização de métricas no Analysis Workspace

As métricas podem ser usadas de várias maneiras no Analysis Workspace. Para obter informações sobre como adicionar métricas e outros tipos de componentes ao Analysis Workspace, consulte [Usar componentes no Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Usar métricas](https://video.tv.adobe.com/v/40817?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]



## Criar métricas calculadas

Métricas calculadas permitem ver facilmente como as métricas se relacionam entre si usando operadores simples ou funções estatísticas.

Há várias maneiras de criar métricas calculadas. O método escolhido determina se a métrica calculada estará disponível na lista de componentes em todos os projetos ou somente no projeto em que foi criada.

### Criar métricas calculadas para todos os projetos

Você pode usar o construtor de métrica calculada para criar métricas calculadas. Quando criadas dessa forma, as métricas calculadas ficam disponíveis na lista de componentes e podem ser usadas em projetos em toda a organização.

Para obter informações sobre como acessar o construtor de métricas calculadas, consulte [Criar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

### Criar métricas calculadas para um único projeto

Você pode criar métricas calculadas rápidas que só estão disponíveis para o projeto em que foram criadas.

Para criar uma métrica calculada para um único projeto:

1. No Analysis Workspace, abra o projeto em que deseja criar a métrica calculada.

1. Em uma tabela de forma livre, clique com o botão direito do mouse em uma ou mais células de coluna de cabeçalho e selecione **[!UICONTROL Criar métrica a partir da seleção]**

   ![Destaque do painel do Workspace Criar a partir da seleção](assets/create-metric-from-selection.png)

1. Para criar uma métrica calculada somente para este projeto, escolha uma das seguintes opções:

   * [!UICONTROL **Dividir**]

   * [!UICONTROL **Subtrair**]

   * [!UICONTROL **Adicionar**]

   * [!UICONTROL **Multiplicar**]

   Ou, para abrir o construtor de métrica calculada e criar a métrica calculada para todos os projetos, selecione [!UICONTROL **Abrir no Construtor de métrica calculada**] e continue com [Criar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

[Métricas calculadas: métricas sem implementação](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=pt-BR) (3:42)

## Comparar métricas com diferentes modelos de atribuição

Se você quiser comparar um modelo com outro de maneira fácil e rápida, clique com o botão direito em uma métrica e selecione **[!UICONTROL Comparar modelos de atribuição]**:

![Comparar atribuição](assets/compare-attribution.png)

Esse atalho permite comparar de forma rápida e fácil um modelo de atribuição com outro, sem arrastar uma métrica e configurá-la duas vezes.

## Usar a função [!UICONTROL média cumulativa] para aplicar a suavização de métricas

Veja um vídeo sobre este tópico:


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Média cumulativa](https://video.tv.adobe.com/v/27068?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

