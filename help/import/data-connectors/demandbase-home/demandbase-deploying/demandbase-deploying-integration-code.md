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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Implantação do código de integração{#deploying-the-integration-code}

Após concluir o assistente de integração, você deve implantar o código de integração no código de implantação do Adobe Analytics (s_ code).

>[!NOTE]
>
>Se você usou o Adobe tagmanager ou o Gerenciamento dinâmico de tags para implantar o Adobe Analytics, é possível adicionar o código de integração com facilidade usando uma dessas ferramentas.

1. Vá até a **[!UICONTROL guia Suporte]** e baixe e salve o `integration code v2_0_1` recurso na área Recursos da integração.

1. Se aplicável, faça as modificações necessárias no código para obter mais informações, consulte [Modificar o código de integração](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855).
1. Inclua o Módulo de integração se ele ainda não estiver presente no código de implantação do Adobe Analytics. Para obter mais informações, consulte [Inclusão do módulo de integração](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e).
1. Implante o código usando um dos seguintes métodos:

   * Use o Adobe tagmanager ou o Gerenciamento dinâmico de tags para adicionar o código.
   * Ou forneça o código para o recurso organizacional responsável por atualizar seu código de implantação do Adobe Analytics.

>[!IMPORTANT]
>
>Certifique-se de testar a implantação dessa integração em um ambiente de desenvolvimento/armazenamento temporário antes de implantá-la em um ambiente de produção.

