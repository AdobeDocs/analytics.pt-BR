---
description: Deploying this integration is a simple process that requires the following actions.
seo-description: A implantação dessa integração é um processo simples que requer as seguintes ações.
seo-title: Deploying the Integration
solution: Analytics
subtopic: Qualtrics
title: Implantação da integração
topic: Conectores de dados
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
translation-type: tm+mt
source-git-commit: f326b29bb73fd6e8630957c43dfd89f47b711986

---


# Implantação da integração{#deploying-the-integration}

A implantação dessa integração é um processo simples que requer as seguintes ações.

## Concluindo o Assistente de integração da Adobe{#completing-the-adobe-integration-wizard}

Para ativar a integração, você deve concluir o assistente de integração Qualtrics na interface dos Conectores de dados

1. Navegue até os conectores de dados e inicie o assistente de integração Qualtrics.
1. Selecione o conjunto de relatórios que deseja usar para essa integração e forneça um nome.

   Conclua o assistente de integração, fornecendo as informações descritas nas etapas a seguir. 1. Etapa 1 do **Assistente**

   | Email Address | O endereço de email do contato principal. |
   |---|---|
   | Descrição | (Opcional) Descrição para esta configuração de integração. |
   | ID da Organização Qualtrics | [Procurando a ID da empresa Qualtrics](../qualtrics-overview/qualtrics-org-id.md) |
   | Token do Adobe SiteCatalyst | [Geração do token do Adobe Analytics Qualtrics](../qualtrics-overview/qualtrics-token.md) |

1. **Etapa 2 do assistente - Mapeamentos** de variáveis| Lista de Resposta Qualtrics| Selecione uma variável de lista disponível em seu conjunto de relatórios. (Talvez seja necessário ativar uma nova listVar no Gerenciador de conjunto de relatórios.)  ||—|—| ID de resposta Qualtrics| Selecione uma eVar ou prop disponível em seu conjunto de relatórios. (Talvez seja necessário ativar uma nova listVar no Gerenciador de conjunto de relatórios.)  || Servidor de rastreamento|Forneça a configuração do servidor de rastreamento (domínio) usada para rastrear os dados do Adobe Analytics. Use o servidor de `trackingServerSecure` rastreamento se ele for diferente da configuração padrão do servidor de rastreamento.  || Submissões de Inquérito Qualtrics| Selecione um evento disponível em seu conjunto de relatórios (talvez seja necessário ativar um novo evento no Gerenciador de conjunto de relatórios).  |

1. **Etapa 3** do Assistente: Nada necessário, apenas informativo.

   Step Result 1. **Etapa 4 do assistente - Configurações de exportação**

   | eVar | Select up to five of your eVars to expose for exporting to Qualtrics |
   |---|---|
   | Eventos | Selecione até cinco dos eventos personalizados a serem expostos para exportação para o Qualtrics |
   | Props | Selecione até cinco de suas Props para expor para exportação para o Qualtrics |
   | Access Requests | Check the box for any of the standard metrics and dimensions that you wish to export to Qualtrics. The  is required to allow the export to function properly.`visitor_id` |

1. **Wizard Step 5: Review configuration and then click Activate Now.******

## Enabling the Integration in Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

After completing the integration wizard, you must activate the integration for each Qualtrics survey that you want connected.

1. Log in to the Qualtrics Research Suite.
1. On the My Surveys tab, click the Edit button for the survey that you want to integrate.********
1. Click the Advanced Options menu and select Adobe Analytics. ******** (if you do not see this option, ask your administrator about gaining the permissions required).

   ![](assets/advanced_options.png)

1. Select the Adobe Analytics Configuration, then click Save. **** Se nenhuma configuração estiver disponível, você provavelmente ainda não concluiu o Assistente de integração da Adobe.
   1. The Include Partial Responses checkbox can be used to indicate that you’d like to capture data into Adobe Analytics after each partial survey screen is completed. **** If not checked, then data is transferred only for fully completed surveys.
   1. The Send Timestamp With Beacon checkbox should be used only when integrating with a Report Suite that is configured to receive time-stamped data (not common).****
   ![](assets/integration_config.png)

## Verificação da integração{#verifying-the-integration}

Depois que todas as etapas de implantação forem concluídas, você poderá validar se a integração está transferindo dados com êxito.

1. **Log** de atividades de integração: Na interface do usuário dos Conectores de dados, consulte a guia **[!UICONTROL Suporte]** na integração Qualtrics. Sob o título Log **[!UICONTROL de atividade de]** integração, você deve ver entradas que indicam dados de classificação bem-sucedidos importados.

   >[!NOTE]
   >
   >Essas entradas devem aparecer dentro de 1 hora após a implantação bem-sucedida.

   ![](assets/verify-1.png)

1. **Dados** de relatório: Visualize seus relatórios de pesquisa Qualtrics com a interface do usuário de relatórios e análises de marketing navegando nos relatórios de pesquisa Qualtrics (em Variáveis **[!UICONTROL de]** lista).

   >[!NOTE]
   >
   >Esses dados devem aparecer dentro de 24 a 48 horas após a implantação bem-sucedida, supondo que a pesquisa integrada esteja recebendo respostas ativamente.

   ![](assets/verify-2.png) ![](assets/verify-3.png)


