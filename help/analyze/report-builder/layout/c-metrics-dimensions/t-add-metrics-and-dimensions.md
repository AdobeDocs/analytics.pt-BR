---
description: Etapas para adicionar métricas e dimensões a uma solicitação.
title: Adicionar métricas e dimensões
topic: Report builder
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Adicionar métricas e dimensões

Etapas para adicionar métricas e dimensões a uma solicitação.

1. [Crie a solicitação](/help/analyze/report-builder/data-requests/data-requests.md) de dados no [!UICONTROL Request Wizard: Step 1]e clique em **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2], double-click metrics, or drag them to the desired position.

   ![Informações da etapa](assets/adding_metrics.png)

   When you add metrics, they are not removed from the [!UICONTROL Metrics] tab, because you can display metrics multiple times within a request. Por exemplo, você pode exibir o subtotal da métrica além de cada valor. No entanto, a lista de métricas disponíveis muda toda vez que você adiciona ou remove uma dimensão.

   You can add only metrics to the [!UICONTROL Metrics] layout section. As métricas são adicionadas ao [!UICONTROL Column Label] layout como um [!UICONTROL Metric Header]. If you move a [!UICONTROL Metric Header] from [!UICONTROL Column Layout] to [!UICONTROL Row Layout], it is displayed there and is used as a metric as a breakdown.

   Observe que uma barra de pesquisa aparece na guia Métricas, logo acima da lista de Métricas.

   ![](assets/search_bar_metric.png)

   Lembre-se:

   * À medida que você insere um termo de pesquisa, a lista será atualizada automaticamente para exibir somente as métricas cujos rótulos correspondem ao termo de pesquisa.
   * A correspondência não diferencia maiúsculas de minúsculas, e é equivalente a uma pesquisa com &quot;contém&quot;.
   * Pesquisas por palavras completas ou outro sinalizador de pesquisa especial (começa com, termina com, E, OU etc.) não são suportados.

      O termo de pesquisa será apagado se você sair do Assistente de pesquisa (isto é, clicar em Concluir ou Cancelar), voltar para a Etapa 1 do Assistente de pesquisa ou alterar a categoria Métrica.

      O termo de pesquisa não será apagado nos seguintes casos:

   * Ao arrastar e soltar (ou clicar duas vezes) um item de métrica da lista para que ele seja adicionado ao Painel de métricas de layout dinâmico/personalizado.
   * Ao remover os itens da métrica do Painel de métricas de layout dinâmico/personalizado.
   * Ao clicar na guia Dimensão e, em seguida, retornar para a guia Métrica.
   * Ao invocar outros subformulários (modal ou sem modo) que retornarão à Etapa 2 do Assistente de solicitações ao sair. Os exemplos de formulários são

      * Formulários de filtro de dimensão
      * Formulários de formatação por intervalos de datas
      * Formulário de opções de formato
      * Formulário de texto anterior-posterior
      * Formulário de localização do intervalo de saída

1. (Opcional) Para classificar uma solicitação por métrica, apenas clique na etiqueta da métrica.
1. Adicionar dimensões da mesma maneira que adiciona métricas.

On the [!UICONTROL Dimensions] tab, the system displays dimensions that break down or are a classification of any base report you select on Step 1, and on the configuration of the report suite. Quando você solta uma dimensão nas grades do layout, ela é removida da visualização em árvore e recalcula a lista de dimensões disponíveis restantes.

The [!UICONTROL Date] dimension is added automatically. Available date dimensions change depending on the selected granularity from the [!UICONTROL Request Wizard: Step 1]. (Os valores válidos são:

    * Hora
    * Dia
    * Semana
    * Mês
    * Ano
    * Intervalo de datas (quando nenhuma granularidade é especificada)

1. Modifique métricas e dimensões configurando opções e filtros de [formato](/help/analyze/report-builder/layout/t-format-display-headers.md).
1. Clique em **[!UICONTROL Finish]**.
In the following example, dimensions relate to the [!UICONTROL Page] metric. Aqui, a [!UICONTROL Referring Domain] dimensão cria um relatório de detalhamento entre [!UICONTROL Page] e [!UICONTROL Referring Domain]. The [!UICONTROL Dimension] tab is updated with only dimensions that you can add to a breakdown report.

![](assets/page_pageview_02.png)
