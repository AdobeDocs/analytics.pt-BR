---
description: 'null'
title: Implantar a integração
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Implantar a integração {#deploying-the-integration}

A implantação dessa integração é um processo simples que consiste em concluir o Assistente de integração da Adobe, implantar o código do plug-in (JavaScript) e verificar a integração.

## Concluir o Assistente de integração da Adobe {#complete-the-adobe-integration-wizard}

Para ativar a integração, conclua o assistente de configuração na interface dos Conectores de dados.

1. Faça logon na Adobe Experience Cloud.
1. Navegue até **[!UICONTROL Data Connectors]**.
1. Inicie o assistente de integração do Kampyle.
1. Selecione o conjunto de relatórios desejado e forneça um nome para a integração.
1. Configure os seguintes itens:
   1. **[!UICONTROL Email address]**: O endereço de email do contato principal.
   1. **[!UICONTROL Description]** (opcional): Descrição desta configuração de integração.
   1. **[!UICONTROL Kampyle Key]**: Localize essa chave no aplicativo Kampyle em **[!UICONTROL Feedback Form]** > **[!UICONTROL Feedback Form Customization]**.
   1. **[!UICONTROL Tracking Server]**: O valor do servidor de rastreamento usado para rastrear os dados do Adobe Analytics.
   1. **[!UICONTROL Tracking Server Secure]**: Se o servidor de rastreamento for diferente para tráfego seguro/https, forneça essa configuração aqui.
1. Configure the following **[!UICONTROL Variable Mappings]** items:
   1. **[!UICONTROL Kampyle Feedback ID]**: Selecione uma variável eVar disponível no conjunto de relatórios
   1. **[!UICONTROL Feedback Grade]**: Selecione um evento bem-sucedido disponível (digite &quot;contador&quot;) no conjunto de relatórios.
   1. **[!UICONTROL Feedback Items]**: Selecione um evento bem-sucedido disponível (digite &quot;contador&quot;) no conjunto de relatórios.
   1. **[!UICONTROL Feedback with Grade]**: Selecione um evento bem-sucedido disponível (digite &quot;contador&quot;) no conjunto de relatórios.
1. Marque a caixa para que o painel Integração do Kampyle seja criado automaticamente (recomendado).
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

## Implante o objeto de configuração de integração {#deploy-the-integration-configuration-object}

Após concluir o assistente de integração, implante o objeto de configuração de integração na propriedade da Web. Em muitos casos, a maneira mais fácil de implantar o objeto de configuração de integração é incluí-lo no código de implantação do Adobe Analytics.

>[!NOTE] Se você usar o Adobe Experience Platform Launch, poderá adicionar facilmente o objeto de configuração de integração por meio dessa ferramenta.

1. Navigate to the **[!UICONTROL Resources]** > **[!UICONTROL Support]** tab of the integration.
1. Baixe e salve o **[!UICONTROL Kampyle Integration Code (JS)]** recurso. O código é semelhante a este:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Implante o código usando um dos seguintes métodos:

   * Use o Adobe Experience Platform Launch.
   * Forneça o código ao recurso organizacional que mantém a implantação do Adobe Analytics.

## Verificar a integração {#verify-the-integration}

Valide se a integração transfere dados com êxito, concluindo algumas verificações.

### Log de atividade de integração {#section-0472df9180db4f218db5f6040cab07af}

View your Kampyle integration setup within the Adobe Experience Cloud by navigating to **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]**. Under the **[!UICONTROL Data In]** tab, you should see entries stating that classification data was successfully imported.

>[!NOTE] As entradas de registro normalmente são exibidas dentro de 24 horas após a implantação bem-sucedida.

![Registro de atividades de integração](assets/integration_activity_log.png)

### Dados de relatórios da Adobe {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Visualize seus relatórios de feedback do Kampyle com o Adobe Analytics navegando até os relatórios do Kampyle localizados na estrutura de menu adequada.

>[!NOTE] Os dados de relatório devem aparecer dentro de 24 a 48 horas após o sucesso da implantação, supondo que os formulários de feedback integrados estejam recebendo envios ativamente.

![Dados de relatórios da Adobe](assets/adobe_reporting_data.png)
