---
description: A implantação dessa integração é um processo simples de três etapas.
title: Implantar a integração
uuid: c578bf26-34c2-44ea-8e60-2990273f8659
translation-type: ht
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# Implantar a integração {#deploying-the-integration}

A implantação dessa integração é um processo simples de três etapas.

## Concluir o Assistente de integração {#completing-the-integration-wizard}

Para ativar a integração você deve concluir o assistente de integração do Selligent na interface dos Data Connectors.

1. Navegue até a área Data Connectors na Adobe Experience Cloud.

   ![](assets/selligent-data_connectors.png)

1. Em **[!UICONTROL Adicionar integrações]**, arraste e solte o plug-in do Selligent na Adobe Experience Cloud.

   ![](assets/selligent-add_integration.png)

   Isso abrirá a integração do Selligent Data Connector.

1. **Configurações de integração**: escolha o Conjunto de relatórios desejado e forneça um nome para a integração em **[!UICONTROL Configurações de integração]**.

1. Em **[!UICONTROL Valores personalizados]**, preencha todas as informações relacionadas à conta do Selligent.

   ![](assets/selligent-general_settings.png)

1. **Mapeamento de variáveis**: escolha as eVars e os eventos reservados apropriados nos menus suspensos:

   ![](assets/selligent-variables.png)

1. **Configurações de dados**: você pode escolher seus próprios segmentos em **[!UICONTROL Seus segmentos]**, exceto os três segmentos automatizados do **[!UICONTROL Partner]**.

1. Essa integração pode exigir o download de alguns pontos de dados para sua conta do Selligent. Você pode optar por conceder acesso à integração em **[!UICONTROL Solicitação de acesso]**.
1. Em **[!UICONTROL Coleta de dados]**, escolha entre uma solução automatizada ou manual (Plug-in do JavaScript) para coletar parâmetros de string de consulta do URL da página inicial. Se você escolher uma solução automatizada, digite o parâmetro da string de consulta para a ID de mensagem e a ID de destinatário, MID e RID, respectivamente. Para obter um plug-in do JavaScript, entre em contato com seu consultor da Adobe.
1. **Configurações do relatório**: em **[!UICONTROL Geração de painel]**, marque a caixa para que o painel do Selligent seja gerado automaticamente.

   ![](assets/selligent-report_settings.png)

1. Revise o resumo da integração e clique em **[!UICONTROL Ativar]**.

## Configuração no Selligent {#configuration-within-selligent}

Assim que a integração estiver ativada no Adobe Analytics, uma configuração automática será ativada no lado do Selligent.

Foi criado um rastreador que rastreará cada email. Caso deseje limitá-lo a um determinado domínio, atualize a configuração do rastreador.

Recomendamos que você mova o parâmetro de rastreamento do Adobe Analytics no URL para a frente. Isso garantirá que as regras de processamento da Adobe capturem os parâmetros do URL da página inicial. Ative o rastreamento marcando a caixa de seleção como mostrado abaixo.

![](assets/selligent-tracker.png)

## Verificar a integração {#verifying-the-integration}

Depois que todas as etapas de implantação forem concluídas você poderá validar se a integração está transferindo dados com êxito.

Vai levar alguns dias para a troca de dados começar. Entre em contato com a Selligent depois de ativar a integração.

### Log de atividade de integração {#section-927e270495db479fba9578915d9ae9c9}

Navegue até sua integração do Selligent nos Data Connectors. Na guia **[!UICONTROL Suporte]**, deve ser possível ver eventos como Dados de métrica importados e/ou Dados de classificação importados com êxito:

![](assets/selligent-verifying.png)

### Dados de relatório {#section-ebd481a162324e66bd6dc8cb4b8d2424}

Visualize seus relatórios de mensagens do Selligent com as métricas apropriadas.

1. Vá para Reports and Analytics na Adobe Experience Cloud.
1. Selecione o conjunto de relatórios adequados.
1. Em **[!UICONTROL Conversões personalizadas]**, selecione os **[!UICONTROL Relatórios de IDs de mensagem]** e escolha **[!UICONTROL ID da mensagem/Nome da mensagem]**.
