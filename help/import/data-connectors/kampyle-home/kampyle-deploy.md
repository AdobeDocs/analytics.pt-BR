---
description: Implante o conector de dados do Kampyle no Adobe Analytics.
title: Implantar a integração
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 46%

---


# Implantar a integração {#deploying-the-integration}

A implantação dessa integração é um processo simples que consiste em concluir o Assistente de integração da Adobe, implantar o código do plug-in (JavaScript) e verificar a integração.

## Concluir o Assistente de integração da Adobe {#complete-the-adobe-integration-wizard}

Para ativar a integração, conclua o assistente de configuração na interface do Data Connectors.

1. Faça logon na Adobe Experience Cloud.
1. Navegue até **[!UICONTROL Data Connectors]**.
1. Inicie o assistente de integração do Kampyle.
1. Selecione o conjunto de relatórios desejado e forneça um nome para a integração.
1. Configure os seguintes itens:
   1. **[!UICONTROL Endereço]** de email: O endereço de email do contato principal.
   1. **[!UICONTROL Descrição]**  (opcional): Descrição dessa configuração de integração.
   1. **[!UICONTROL Chave]** Kampyle: Localize essa chave no aplicativo Kampyle, em  **[!UICONTROL Formulário de feedback]**  > Personalização do formulário de  **[!UICONTROL feedback]**.
   1. **[!UICONTROL Servidor]** de rastreamento: O valor do servidor de rastreamento usado para rastrear os dados do Adobe Analytics.
   1. **[!UICONTROL Servidor de rastreamento seguro]**: Se o servidor de rastreamento for diferente para tráfego seguro/https, forneça essa configuração aqui.
1. Configure os itens de **[!UICONTROL Mapeamentos de variável]** a seguir:
   1. **[!UICONTROL ID]** de feedback do Kampyle: Selecione uma variável eVar disponível no conjunto de relatórios
   1. **[!UICONTROL Nota de feedback]**: Selecione um evento bem-sucedido disponível (digite &quot;contador&quot;) no conjunto de relatórios.
   1. **[!UICONTROL Itens]** de feedback: Selecione um evento bem-sucedido disponível (digite &quot;contador&quot;) no conjunto de relatórios.
   1. **[!UICONTROL Feedback com nota]**: Selecione um evento bem-sucedido disponível (digite &quot;contador&quot;) no conjunto de relatórios.
1. Marque a caixa para que o painel Integração do Kampyle seja criado automaticamente (recomendado).
1. Revise todos os itens de configuração e clique em **[!UICONTROL Ativar agora]**.

## Implante o objeto de configuração de integração {#deploy-the-integration-configuration-object}

Após concluir o assistente de integração, implante o objeto de configuração de integração na propriedade da Web. Em muitos casos, a maneira mais fácil de implantar o objeto de configuração de integração é incluí-lo no código de implantação do Adobe Analytics.

>[!NOTE]
>
>Se você usar o Adobe Experience Platform Launch, poderá adicionar facilmente o objeto de configuração de integração por meio dessa ferramenta.

1. Navegue até a guia **[!UICONTROL Recursos]** > **[!UICONTROL Suporte da integração]**.
1. Baixe e salve o recurso **[!UICONTROL Código de integração do Kampyle (JS)]**. O código é semelhante a este:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Implante o código usando um dos seguintes métodos:

   * Use o Adobe Experience Platform Launch.
   * Forneça o código ao recurso organizacional que mantém a implantação do Adobe Analytics.

## Verificar a integração {#verify-the-integration}

Valide se a integração transfere dados com êxito concluindo algumas verificações.

### Log de atividade de integração {#section-0472df9180db4f218db5f6040cab07af}

Visualize sua configuração de integração do Kampyle na Adobe Experience Cloud navegando até **[!UICONTROL Suporte]** > **[!UICONTROL Log de atividade de integração]**. Na guia **[!UICONTROL Entrada de dados]**, você deve ver entradas declarando que os dados de classificação foram importados com êxito.

>[!NOTE]
>
>As entradas de log normalmente são exibidas dentro de 24 horas após o sucesso da implantação.

![Log de atividades de integração](assets/integration_activity_log.png)

### Dados de relatórios da Adobe {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Visualize seus relatórios de feedback do Kampyle com o Adobe Analytics navegando até os relatórios do Kampyle localizados na estrutura de menu adequada.

>[!NOTE]
>
>Os dados de relatório devem aparecer dentro de 24 a 48 horas após o sucesso da implantação, supondo que os formulários de feedback integrados estejam recebendo envios ativamente.

![Dados de relatórios da Adobe](assets/adobe_reporting_data.png)
