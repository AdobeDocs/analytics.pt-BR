---
description: Após concluir o assistente de integração, você deve implantar o código de integração no código de implantação do Adobe Analytics (s_ code).
seo-description: Após concluir o assistente de integração, você deve implantar o código de integração no código de implantação do Adobe Analytics (s_ code).
seo-title: Implantação do código de integração
title: Implantação do código de integração
uuid: b 3 fbda 0 b -4 ed 3-4967-84 ee -6 c 66564606 e 7
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Deploying the Integration Code{#deploying-the-integration-code}

Após concluir o assistente de integração, você deve implantar o código de integração no código de implantação do Adobe Analytics (s_ code).

>[!NOTE]
>
>Se você usou o Adobe tagmanager ou o Gerenciamento dinâmico de tags para implantar o Adobe Analytics, é possível adicionar o código de integração com facilidade usando uma dessas ferramentas.

1. Go to the **[!UICONTROL Support]** tab and download and save the `integration code v2_0_1` resource from the Resources area of the integration.

1. If applicable, make any necessary modifications to the code For more information, see [Modifying the Integration Code](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855).
1. Inclua o Módulo de integração se ele ainda não estiver presente no código de implantação do Adobe Analytics. For more information, see [Including the Integrate Module](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e).
1. Implante o código usando um dos seguintes métodos:

   * Use o Adobe tagmanager ou o Gerenciamento dinâmico de tags para adicionar o código.
   * Ou forneça o código para o recurso organizacional responsável por atualizar seu código de implantação do Adobe Analytics.

>[!IMPORTANT]
>
>Certifique-se de testar a implantação dessa integração em um ambiente de desenvolvimento/armazenamento temporário antes de implantá-la em um ambiente de produção.

