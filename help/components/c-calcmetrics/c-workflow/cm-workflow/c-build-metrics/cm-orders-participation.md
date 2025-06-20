---
description: Explica como criar uma métrica que exibe quais Canais de marketing fornecem assistência em impulsionar pedidos. Isso pode ser adaptado a qualquer dimensão ou evento de sucesso de seu interesse.
title: métrica Assistências em pedidos
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: bf58da2a39e8b9fd298356f23a9bf8f6c394d3de
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 25%

---

# Criar uma métrica calculada mais complexa

Este artigo explica um exemplo mais complexo de uma métrica calculada. Essas métricas calculadas mostram quais Canais de marketing auxiliam na criação de pedidos. Esse tipo de métrica calculada pode ser adaptado a qualquer dimensão ou evento bem-sucedido.

1. Comece a criar uma métrica calculada, conforme descrito em [Criar métricas](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. No Criador de métricas calculadas, nomeie a métrica `Assisted Orders` ou algo semelhante.

1. Selecione a métrica **[!UICONTROL Pedidos online]** dos componentes de **[!UICONTROL Métricas]** e arraste a métrica para a área **[!UICONTROL Definição]**.

   1. Selecione ![Configuração](/help/assets/icons/Setting.svg) para a métrica.
   1. Selecione **[!UICONTROL Usar modelo de atribuição não padrão]**.
   1. Ajuste o modelo de atribuição no **[!UICONTROL Modelo de atribuição de coluna]**.
      1. Selecione **[!UICONTROL Personalizado]** para **[!UICONTROL Modelo]**. Defina **[!UICONTROL Iniciante]** para `0`, **[!UICONTROL Reprodutor]** para `100` e **[!UICONTROL Mais próximo]** para `0`.
      1. Selecione **[!UICONTROL Visitante]** para **[!UICONTROL Contêiner]**.
      1. Selecione **[!UICONTROL 30 Dias]** para **[!UICONTROL Janela de pesquisa]**.

      1. Selecione **[!UICONTROL Aplicar]**.

      ![Modelo de atribuição de coluna](assets/complex-calculated-metric.png)

1. Selecione **[!UICONTROL Salvar]** para salvar a métrica calculada.

Para usar a métrica calculada:

1. No Analysis Workspace, crie uma tabela de forma livre com a dimensão **[!UICONTROL Canal de marketing]**, **[!UICONTROL Pedidos online]** e sua nova métrica **[!UICONTROL Pedidos online assistidos]**.

   ![Pedidos Online Assistidos por Canal de Marketing](assets/marketing-channel-assists.png)

1. (Opcional) Compartilhe a métrica com outros usuários em sua organização, conforme descrito em [Compartilhar métricas calculadas](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).

Esse é um jeito fácil de averiguar quais Canais de marketing assistiram em impulsionar pedidos. Como alternativa, em uma tabela de forma livre, você pode clicar com o botão direito do mouse em qualquer métrica e ajustar o modelo de atribuição diretamente da tabela.
