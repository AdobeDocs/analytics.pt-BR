---
description: Depois de concluir o assistente de integração, você deve implantar o objeto de configuração de integração em sua propriedade da Web.
seo-description: Depois de concluir o assistente de integração, você deve implantar o objeto de configuração de integração em sua propriedade da Web.
seo-title: Implantar o objeto de configuração de integração
solution: Analytics
title: Implantar o objeto de configuração de integração
uuid: e 951 c 864-2914-4324-9 f 03-5069 d 4 f 75 d 99
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Implantar o objeto de configuração de integração{#deploy-the-integration-configuration-object}

Depois de concluir o assistente de integração, você deve implantar o objeto de configuração de integração em sua propriedade da Web.

Em muitos casos, a maneira mais fácil de implantar o objeto de configuração de integração é incluí-lo com o código de implantação do Adobe Analytics.

>[!NOTE]
>
>Se você usar o Adobe tagmanager ou o Gerenciamento dinâmico de tags para implantar o Adobe Analytics, poderá adicionar facilmente o objeto de configuração de integração por meio dessa ferramenta.

1. Navegue até **[!UICONTROL Recursos]** &gt; **[!UICONTROL guia Suporte]** da integração.
1. Baixe e salve o recurso de Código de integração **[!UICONTROL Kampyle (JS)]** . O código é semelhante a isto:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Implante o código usando um dos seguintes métodos:

       | ** Você usa o Adobe tagmanager ou o Gerenciamento dinâmico de tags.** | Use a interface do gerenciamento de tags para adicionar o código. |
    |—|—|
    | ** Em todos os outros casos** | Forneça o código ao recurso organizacional responsável por atualizar seu código de implantação do Adobe Analytics. |
   
