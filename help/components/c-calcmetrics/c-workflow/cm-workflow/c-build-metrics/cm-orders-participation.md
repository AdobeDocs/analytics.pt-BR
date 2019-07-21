---
description: Explica como criar uma métrica que exibe quais Canais de marketing fornecem assistência em impulsionar pedidos. Isso pode ser adaptado a qualquer dimensão ou evento de sucesso de seu interesse.
seo-description: Explica como criar uma métrica que exibe quais Canais de marketing fornecem assistência em impulsionar pedidos. Isso pode ser adaptado a qualquer dimensão ou evento de sucesso de seu interesse.
seo-title: Métrica de auxílio de pedidos
title: Métrica de auxílio de pedidos
uuid: 7 c 82227 a -7 fcc -486 f-bef 8-164 ea 84 af 77 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Métrica de auxílio de pedidos

Explica como criar uma métrica que exibe quais Canais de marketing fornecem assistência em impulsionar pedidos. Isso pode ser adaptado a qualquer dimensão ou evento de sucesso de seu interesse.

1. No Construtor de métricas calculadas, nomeie a métrica “Pedidos com assistência”.
1. Na tela de Definição, arraste uma métrica de Pedidos. Em seguida, ajuste o modelo de atribuiçao por meio da engrenagem de configurações, marcando a caixa de seleção **[!UICONTROL Usar modelos de atribuição não padrão].**

   ![](assets/attr-model.png)

1. Selecione **[!UICONTROL Personalizado]como o modelo de atribuição.** Altere os valores para 0 (início), 100 (reprodução) e 0 (encerramento).

   ![](assets/custom-attr-model.png)

1. Salve a métrica.
1. Crie uma tabela de forma livre na Analysis Workspace com a dimensão Canal de marketing, Pedidos e sua nova métrica Pedidos com assistência.

   ![](assets/mktg-channel-assists.png)

Esse é um jeito fácil de averiguar quais Canais de marketing assistiram em impulsionar pedidos. Como alternativa, em uma tabela de forma livre, você pode clicar com o botão direito do mouse em qualquer métrica e ajustar o modelo de atribuição diretamente da tabela.
