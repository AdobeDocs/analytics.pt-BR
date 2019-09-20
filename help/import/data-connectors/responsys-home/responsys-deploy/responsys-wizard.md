---
description: Etapas para concluir o assistente de integração na interface dos Conectores de dados.
seo-description: Etapas para concluir o assistente de integração na interface dos Conectores de dados.
seo-title: Concluindo o Assistente de integração da Adobe
solution: Analytics
title: Concluindo o Assistente de integração da Adobe
uuid: fb106251-78cf-4a2a-8ba2-2a39188ba910
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Concluindo o Assistente de integração da Adobe{#completing-the-adobe-integration-wizard}

Etapas para concluir o assistente de integração na interface dos Conectores de dados.

1. Navegue até a área Conectores de dados (anteriormente Genesis) na Adobe Experience Cloud.
1. Inicie o assistente de integração do Responsys.
1. Escolha o Conjunto de relatórios desejado e forneça um nome para a integração.
1. Configure os seguintes itens:

   | Item | Descrição |
   |---|---|
   | Endereço de email | O endereço de email do contato principal |
   | Descrição | (Opcional) Descrição para esta configuração de integração |
   | ID da Conta | Obtido ao entrar em contato com a equipe de suporte da Responsys em support@responsys.com |

1. Configure os seguintes itens de Mapeamentos **[!UICONTROL de]** variável:

   | Item | Descrição |
   |---|---|
   | ID da mensagem | Selecione uma eVar para coletar IDs de mensagem em tempo real. |
   | Recipient ID | Selecione uma eVar para coletar IDs de destinatários em tempo real. |
   | Total de rejeições | Selecione um evento numérico para receber rejeições diárias de Responsys. |
   | Email enviado | Selecione um evento numérico para receber envios diários do Responsys. |
   | Clicado | Selecione um evento numérico para receber o total diário de cliques de Responsys. |
   | Aberto | Selecione um evento numérico para receber o total diário de aberturas do Responsys. |
   | Inscrito | Selecione um evento numérico para receber cancelamentos diários de assinaturas do Responsys. |
   | Entregue | Selecione um evento numérico para receber entregas diárias de Responsys. |

1. Habilite o acesso aos dados e configure a coleta de dados.
   1. Renomeie as classificações conforme necessário.
   1. **[!UICONTROL Segmentos]** de parceiros são segmentos padrão de remarketing que estão incluídos na sua integração.
   1. Em Solicitações **[!UICONTROL de]** acesso, marque a caixa para permitir que as informações do produto sejam exportadas para a Responsys em segmentos diários de recomercialização.
   1. Configure se você coletará IDs atualizando manualmente seu código de coleta do Analytics ou usando a solução automatizada. Se você selecionar Solução **** automatizada, deverá incluir os parâmetros usados em links de email para passar IDs.
1. Revise todos os itens de configuração e clique em **[!UICONTROL Ativar agora]**.
