---
description: Com o Criador de métricas calculadas, qualquer um pode criar uma métrica de participação.
title: Métrica de participação
feature: Calculated Metrics
exl-id: bef185d6-72c0-4068-80f8-57261369573f
source-git-commit: 4bf8397ee979614539baf21b36363eb03357567a
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 37%

---

# Criar uma métrica “Participação”

As informações a seguir explicam como criar uma métrica que mostra quais páginas contribuíram para (ou participaram de) visitas que continham um pedido.

Esse tipo de informação pode ser útil para qualquer proprietário de conteúdo.

>[!NOTE]
>
>Você pode ativar as métricas de participação nas Ferramentas administrativas, mas somente para eventos personalizados 1 - 100.

1. Comece a criar uma métrica calculada, conforme descrito em [Criar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. No Criador de métricas calculadas, nomeie a métrica como &quot;Participação&quot;.

1. Arraste o evento bem sucedido &quot;Pedido&quot; para a tela Definição.

1. Altere o [modelo de atribuição](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) desse evento para **[!UICONTROL Participação]** na engrenagem **[!UICONTROL Configurações]**. Selecione o lookback **[!UICONTROL Visita]**. A definição deve ficar parecida com isto:

   ![](assets/participation.png)

1. Selecione [!UICONTROL **Salvar**] para salvar a métrica.

1. Use a métrica calculada em um relatório de **[!UICONTROL Páginas]**.

   ![](assets/participation-pages.png)

1. (Opcional) Compartilhe a métrica com outros usuários em sua organização, conforme descrito em [Compartilhar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).
