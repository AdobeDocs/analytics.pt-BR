---
description: Com o Criador de métricas calculadas, qualquer um pode criar uma métrica de participação.
seo-description: Com o Criador de métricas calculadas, qualquer um pode criar uma métrica de participação.
seo-title: Métrica de participação
title: Métrica de participação
uuid: 7 cb 191 be-bc 4 e -46 ef -8 a 20-ccba 5355 e 253
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Métrica de participação

Este é um caso de uso simples: Você é um proprietário de conteúdo e deseja ver quais páginas contribuíram para (participaram de) visitas que continham um pedido. Veja como:

>[!NOTE]
>
>Você costumava fazer isso por meio das Ferramentas administrativas. Ainda é possível habilitar as métricas de participação nas ferramentas de Admin, mas apanas para eventos personalizados 1 - 100.

Veja um caso de uso simples: um proprietário de conteúdo deseja saber quais páginas contribuíram para (participaram de) visitas com cadastro via email. Veja como:

1. Crie uma nova métrica no Criador de métricas calculadas.
1. Arraste o evento bem-sucedido "Pedidos" para a tela Definição.
1. Change the [attribution model](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) of that event to **[!UICONTROL Participation]** under the **[!UICONTROL Settings]** gear. Select **[!UICONTROL Visit]** lookback. A definição deve ficar parecida com isto:

   ![](assets/participation.png)

1. Salve a métrica.
1. Use the calculated metric in a **[!UICONTROL Pages]** report.

   ![](assets/participation-pages.png)

1. (Opcional) Compartilhe a métrica com outros usuários em sua organização.

