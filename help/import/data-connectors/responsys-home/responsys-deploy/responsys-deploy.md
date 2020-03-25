---
description: 'null'
title: Implantar a integração
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implantar a integração {#deploying-the-integration}

A implantação dessa integração é um processo simples que requer as seguintes ações:

## Concluir o Assistente de integração da Adobe {#completing-the-adobe-integration-wizard}

Etapas para concluir o assistente de integração na interface do Data Connectors.

1. Navegue até a área Data Connectors (anteriormente Genesis) na Adobe Experience Cloud.
1. Inicie o assistente de integração do Responsys.
1. Escolha o Conjunto de relatórios desejado e forneça um nome para a integração.
1. Configure os seguintes itens:

   | Item | Descrição |
   |---|---|
   | Endereço de email | O endereço de email do contato principal |
   | Descrição | (Opcional) Descrição dessa configuração de integração |
   | ID da Conta | Obtido ao entrar em contato com a equipe de suporte da Responsys via support@responsys.com |

1. Configure os itens de **[!UICONTROL Mapeamentos de variável]** a seguir:

   | Item | Descrição |
   |---|---|
   | ID de mensagem | Selecione uma eVar para coletar IDs de mensagem em tempo real. |
   | ID de destinatário | Selecione uma eVar para coletar IDs de destinatários em tempo real. |
   | Total de rejeições | Selecione um evento numérico para receber rejeições do Responsys diariamente. |
   | Email enviado | Selecione um evento numérico para receber envios do Responsys diariamente. |
   | Clicados | Selecione um evento numérico para receber o total de cliques do Responsys diariamente. |
   | Abertos | Selecione um evento numérico para receber o total de aberturas do Responsys diariamente. |
   | Inscrições canceladas | Selecione um evento numérico para receber cancelamentos de inscrição do Responsys diariamente. |
   | Entregues | Selecione um evento numérico para receber entregas do Responsys diariamente. |

1. Habilite o acesso aos dados e configure a coleta de dados.
   1. Renomeie as classificações conforme necessário.
   1. **[!UICONTROL Segmentos de parceiros]** são segmentos padrão de remarketing que estão incluídos na sua integração.
   1. Em **[!UICONTROL Solicitações de acesso]**, marque a caixa para permitir que as informações do produto sejam exportadas para o Responsys em segmentos diários de remarketing.
   1. Configure se você coletará IDs atualizando manualmente o código de coleta do Analytics ou usando a solução automatizada. Se você selecionar **[!UICONTROL Solução automatizada]**, é necessário incluir os parâmetros usados em links de email para transmitir IDs.
1. Revise todos os itens de configuração e clique em **[!UICONTROL Ativar agora]**.

## Configuração dentro do sistema Responsys {#configuring-within-the-responsys-system}

A ativação da integração envolve entrar em contato com o suporte da Responsys.

Após concluir o assistente de integração, você deve ativar a integração dentro do Responsys.

Para isso, entre em contato com a equipe de suporte do Responsys via support@responsys.com.
