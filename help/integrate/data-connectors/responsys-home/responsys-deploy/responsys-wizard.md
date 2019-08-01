---
description: Etapas para concluir o assistente de integração na interface dos Conectores de dados.
seo-description: Etapas para concluir o assistente de integração na interface dos Conectores de dados.
seo-title: Conclusão do Assistente de integração da Adobe
solution: Analytics
title: Conclusão do Assistente de integração da Adobe
uuid: fb 106251-78 cf -4 a 2 a -8 ba 2-2 a 39188 ba 910
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Etapas para concluir o assistente de integração na interface dos Conectores de dados.

1. Navegue até a área Conectores de dados (antigo Genesis) na Adobe Marketing Cloud.
1. Inicie o assistente de integração de Responsys.
1. Escolha o Conjunto de relatórios desejado e forneça um nome para a integração.
1. Configure os seguintes itens:

   | Item | Descrição |
   |---|---|
   | Endereço de email | O endereço de email do contato principal |
   | Descrição | (Opcional) Descrição para essa configuração de integração |
   | ID da Conta | Obtido entrando em contato com a Equipe de suporte da Responsys em support@responsys.com |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   | Item | Descrição |
   |---|---|
   | ID da mensagem | Selecione uma evar para coletar a ID da mensagem em tempo real. |
   | Recipient ID | Selecione uma evar para coletar a ID do destinatário em tempo real. |
   | Total de rejeições | Selecione um evento numérico para receber devoluções diárias de Responsys. |
   | Email enviado | Selecione um evento numérico para receber envios diários de Responsys. |
   | Clicado | Selecione um evento numérico para receber o total diário de cliques de Responsys. |
   | Abertos | Selecione um evento numérico para receber o total diário de Responsys. |
   | Cancelar inscrição | Selecione um evento numérico para receber o cancelamento diário de Responsys. |
   | Entregue | Selecione um evento numérico para receber entregas diárias de Responsys. |

1. Habilite o acesso aos dados e configure a coleta de dados.
   1. Renomeie classificações conforme necessário.
   1. **[!UICONTROL Segmentos de parceiros]** são segmentos padrão de recomercialização incluídos na integração.
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to Responsys in daily remarketing segments.
   1. Configure se você coletará a ID manualmente para atualizar o código de coleta do Analytics ou usando a solução automatizada. If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID’s.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
