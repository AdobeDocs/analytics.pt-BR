---
description: Com o Criador de métricas calculadas, qualquer um pode criar uma métrica de participação.
title: Métrica de participação
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Métrica de participação

Este é um caso de uso simples: Você é um proprietário de conteúdo e deseja ver para quais páginas contribuíram (ou seja, participaram) visitas que continham um pedido. Veja como:

> [!NOTE] Você costumava ter que fazer isso através das Ferramentas administrativas. Ainda é possível habilitar as métricas de participação nas ferramentas de Admin, mas apanas para eventos personalizados 1 - 100.

Veja um caso de uso simples: um proprietário de conteúdo deseja saber quais páginas contribuíram para (participaram de) visitas com cadastro via email. Veja como:

1. Crie uma nova métrica no Criador de métricas calculadas.
1. Arraste o evento bem-sucedido "Pedidos" para a tela Definição.
1. Altere o modelo [de](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) atribuição desse evento para **[!UICONTROL Participação]** na engrenagem **[!UICONTROL Configurações]** . Selecione Pesquisar **[!UICONTROL Visita]** . A definição deve ficar parecida com isto:

   ![](assets/participation.png)

1. Salve a métrica.
1. Use a métrica calculada em um relatório **[!UICONTROL Páginas]** .

   ![](assets/participation-pages.png)

1. (Opcional) Compartilhe a métrica com outros usuários em sua organização.

