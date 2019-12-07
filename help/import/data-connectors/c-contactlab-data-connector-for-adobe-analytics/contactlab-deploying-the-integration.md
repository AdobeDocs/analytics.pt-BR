---
description: 'null'
title: Implantação da integração
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implantação da integração{#deploying-the-integration}

A implantação dessa integração é um processo simples que requer as seguintes ações:

## Conclua o Assistente de integração da Adobe{#completing-the-adobe-integration-wizard}

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

## Verificar a integração{#verifying-the-integration}

Exibir a configuração de integração do ContactLab na Adobe Experience Cloud

1. Exibir o log de atividades de integração.
   1. Na Adobe Experience Cloud, navegue até **[!UICONTROL Suporte]** &gt; Log **[!UICONTROL de atividades de]** integração.

      ![](assets/integration_activity_log.png)

   1. Procure entradas como Dados de **[!UICONTROL classificação importados com êxito]**, Dados de **[!UICONTROL métricas importados com êxito]** e Dados de **[!UICONTROL métricas exportados com êxito]**. Essas entradas devem aparecer dentro de 1 dia após a implantação bem-sucedida.
1. Visualize seus dados de relatório no Adobe Analytics.
   1. Navegue até Conversão **** personalizada &gt; Conversão **[!UICONTROL personalizada 1-10]** &gt; Relatórios **[!UICONTROL de ID da]** mensagem.

      ![](assets/reporting.png)

   1. Procure relatórios do ContactLab. Esses dados devem aparecer entre 24 e 48 horas após a implantação bem-sucedida.
