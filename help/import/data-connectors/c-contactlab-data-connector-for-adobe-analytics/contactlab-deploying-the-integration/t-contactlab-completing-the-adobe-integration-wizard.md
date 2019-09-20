---
description: Etapas para concluir o assistente de integração na interface dos Conectores de dados.
seo-description: Etapas para concluir o assistente de integração na interface dos Conectores de dados.
seo-title: Concluindo o Assistente de integração da Adobe
solution: Analytics
title: Concluindo o Assistente de integração da Adobe
uuid: a8135be3-fba3-436d-8959-faed40b15088
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Concluindo o Assistente de integração da Adobe{#completing-the-adobe-integration-wizard}

Etapas para concluir o assistente de integração na interface dos Conectores de dados.

1. Navegue até a área Conectores de dados (anteriormente Genesis) na Adobe Experience Cloud.
1. Inicie o assistente de integração ContactLab.
1. Escolha o Conjunto de relatórios desejado e forneça um nome para a integração.
1. Configure os seguintes itens:

   | Item | Descrição |
   |---|---|
   | Endereço de email | O endereço de email do contato principal |
   | Descrição | (Opcional) Descrição para esta configuração de integração |

1. Configure os seguintes itens de Mapeamentos **[!UICONTROL de]** variável:

   | Item | Descrição |
   |---|---|
   | ID do link | Selecione uma eVar para coletar IDs de links em tempo real. |
   | ID da mensagem | Selecione uma eVar para coletar IDs de mensagem em tempo real. |
   | Recipient ID | Selecione uma eVar para coletar IDs de destinatários em tempo real. |
   | Devoluções | Selecione um evento numérico para receber saltos diários do ContactLab. |
   | Enviados | Selecione um evento numérico para receber envios diários do ContactLab. |
   | Clicado | Selecione um evento numérico para receber cliques diários do ContactLab. |
   | Aberto | Selecione um evento numérico para receber o total diário de aberturas do ContactLab. |
   | Inscrito | Selecione um evento numérico para receber cancelamentos diários de assinaturas do ContactLab. |

1. Habilite o acesso aos dados e configure a coleta de dados.
   1. Renomeie as classificações conforme necessário.
   1. **[!UICONTROL Segmentos]** de parceiros são segmentos padrão de remarketing que estão incluídos na sua integração.
   1. Em **[!UICONTROL Seus segmentos]**, selecione quaisquer segmentos personalizados que você deseja incluir nesta integração. Você pode criar segmentos personalizados adicionais no painel de administração.
   1. Em Solicitações **[!UICONTROL de]** acesso, marque a caixa para permitir que as informações do produto sejam exportadas para o ContactLab em segmentos diários de recomercialização.
   1. Renomeie as métricas calculadas conforme necessário.
   1. Configure se você coletará IDs atualizando manualmente seu código de coleta do Analytics ou usando a solução automatizada. Se você selecionar Solução **** automatizada, deverá incluir os parâmetros usados em links de email para passar IDs.
1. Revise todos os itens de configuração e clique em **[!UICONTROL Ativar agora]**.
