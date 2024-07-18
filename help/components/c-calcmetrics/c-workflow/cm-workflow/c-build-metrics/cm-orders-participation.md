---
description: Explica como criar uma métrica que exibe quais Canais de marketing fornecem assistência em impulsionar pedidos. Isso pode ser adaptado a qualquer dimensão ou evento de sucesso de seu interesse.
title: métrica Assistências em pedidos
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 59%

---

# Criar uma métrica “Assistências em pedidos”

As informações a seguir explicam como criar uma métrica que mostra quais Canais de marketing auxiliam na criação de pedidos. Isso pode ser adaptado a qualquer dimensão ou evento de sucesso de seu interesse.

1. Comece a criar uma métrica calculada, conforme descrito em [Criar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. No Criador de métricas calculadas, nomeie a métrica &quot;Pedidos assistidos&quot; ou algo semelhante.

1. Na tela de Definição, arraste uma métrica de Pedidos. Em seguida, ajuste o modelo de atribuição por meio da engrenagem de configurações, marcando a caixa de seleção **[!UICONTROL Usar modelos de atribuição não padrão]**.

   ![](assets/attr-model.png)

1. Selecione **[!UICONTROL Personalizado]** como o modelo de atribuição. Altere os valores para 0 (início), 100 (reprodução) e 0 (encerramento).

   ![](assets/custom-attr-model.png)

1. Selecione [!UICONTROL **Aplicar**] > [!UICONTROL **Salvar**].

1. No Analysis Workspace, crie uma tabela de forma livre com a dimensão Canal de marketing, Pedidos e sua nova métrica Pedidos assistidos.

   ![](assets/mktg-channel-assists.png)

   Esse é um jeito fácil de averiguar quais Canais de marketing assistiram em impulsionar pedidos. Como alternativa, em uma tabela de forma livre, você pode clicar com o botão direito do mouse em qualquer métrica e ajustar o modelo de atribuição diretamente da tabela.

1. (Opcional) Compartilhe a métrica com outros usuários em sua organização, conforme descrito em [Compartilhar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).
