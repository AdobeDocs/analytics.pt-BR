---
description: A implantação dessa integração é um processo simples que requer as seguintes ações.
subtopic: Qualtrics
title: Implantar a integração
topic: Data connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implantar a integração {#deploying-the-integration}

A implantação dessa integração é um processo simples que requer as seguintes ações.

## Concluir o Assistente de integração da Adobe {#completing-the-adobe-integration-wizard}

Para ativar a integração você deve concluir o assistente de integração do Qualtrics na interface dos Data Connectors

1. Navegue até os conectores de dados e inicie o assistente de integração do Qualtrics.
1. Selecione o conjunto de relatórios que você deseja usar com essa integração e forneça um nome.

   Conclua o assistente de integração fornecendo as informações descritas nas etapas a seguir. 1. **Etapa 1 do Assistente**

   | Endereço de email | O endereço de email do contato principal. |
   |---|---|
   | Descrição | (Opcional) Descrição dessa configuração de integração. |
   | ID da organização Qualtrics | [Procure a ID da organização do Qualtrics](../qualtrics-overview/qualtrics-org-id.md) |
   | Token do Adobe SiteCatalyst | [Geração do token Qualtrics do Adobe Analytics ](../qualtrics-overview/qualtrics-token.md) |

1. **Etapa 2 do assistente - Mapeamentos de variáveis** | Lista de respostas do Qualtrics | Selecione uma variável de lista disponível em seu conjunto de relatórios. (Talvez seja necessário ativar uma nova listVar no Gerenciador de conjunto de relatórios.)  |
|---|---|
| ID de resposta do Qualtrics | Selecione uma eVar ou prop disponível em seu conjunto de relatórios. (Talvez seja necessário ativar uma nova listVar no Gerenciador de conjunto de relatórios.)  |
|  Servidor de rastreamento  |Forneça a configuração do servidor de rastreamento (domínio) usada para rastrear os dados do Adobe Analytics. Use o servidor de rastreamento `trackingServerSecure` se ele for diferente da sua configuração padrão de servidor de rastreamento.  |
| Envios de pesquisas do Qualtrics | Selecione um evento disponível em seu conjunto de relatórios (talvez seja necessário ativar um novo evento no Gerenciador de conjunto de relatórios).  |

1. **Etapa 3 do Assistente**: nada necessário, apenas informativo.

   Resultado da etapa 1. **Etapa 4 do assistente - Configurações de exportação**

   | eVar | Selecione até cinco de suas eVars a serem expostas na exportação para o Qualtrics |
   |---|---|
   | Events | Selecione até cinco dos eventos personalizados a serem expostos na exportação para o Qualtrics |
   | Props | Selecione até cinco de suas Props a serem expostas na exportação para o Qualtrics |
   | Solicitações de acesso | Marque a caixa para verificar se há métricas e dimensões padrão que você deseja exportar para o Qualtrics. A `visitor_id` é necessária para que funcione corretamente. |

1. **Etapa 5 do assistente**: revise a configuração e clique em **[!UICONTROL Ativar agora]**.

## Ativação da integração no Qualtrics Research Suite {#enabling-the-integration-in-qualtrics-research-suite}

Após concluir o assistente de integração, você deve ativar a integração para cada pesquisa do Qualtrics que você deseja conectar.

1. Faça logon no Qualtrics Research Suite.
1. Na guia **[!UICONTROL Minhas Pesquisas]**, clique no botão **[!UICONTROL Editar]** da pesquisa que você deseja integrar.
1. Clique no menu **[!UICONTROL Opções avançadas]** e selecione **[!UICONTROL Adobe Analytics]**. (se você não vir essa opção, pergunte ao administrador sobre obter as permissões necessárias).

   ![](assets/advanced_options.png)

1. Selecione a Configuração do Adobe Analytics e clique em **[!UICONTROL Salvar]**. Se nenhuma configuração estiver disponível, você provavelmente ainda não concluiu o Assistente de integração da Adobe.
   1. A caixa de seleção **[!UICONTROL Incluir respostas parciais]** pode ser usada para indicar que você gostaria de capturar dados no Adobe Analytics depois que cada tela parcial da pesquisa for concluída. Se não estiver marcada, os dados serão transferidos somente para pesquisas totalmente concluídas.
   1. A caixa de seleção **[!UICONTROL Enviar carimbo de data e hora com beacon]** deve ser usada somente durante a integração com um conjunto de relatórios configurado para receber dados com carimbo de data e hora (não comum).
   ![](assets/integration_config.png)

## Verificar a integração {#verifying-the-integration}

Depois que todas as etapas de implantação forem concluídas você poderá validar se a integração está transferindo dados com êxito.

1. **Log de atividades de integração**: na interface do usuário dos Data Connectors, consulte a guia **[!UICONTROL Suporte]** na integração Qualtrics. Sob o título **[!UICONTROL Log de atividade de integração]**, você deve ver entradas que indicam dados de classificação importados com sucesso.

   >[!NOTE]
   >
   >Essas entradas devem aparecer dentro de 1 hora após o sucesso da implantação.

   ![](assets/verify-1.png)

1. **Dados de relatórios**: visualize seus relatórios de pesquisa do Qualtrics com a interface do usuário do Marketing Reports and Analytics navegando nos relatórios de pesquisa do Qualtrics (em **[!UICONTROL Variáveis de lista]**).

   >[!NOTE]
   >
   >Esses dados devem aparecer dentro de 24 a 48 horas após o sucesso da implantação, supondo que a pesquisa integrada esteja recebendo respostas ativamente.

   ![](assets/verify-2.png) ![](assets/verify-3.png)


