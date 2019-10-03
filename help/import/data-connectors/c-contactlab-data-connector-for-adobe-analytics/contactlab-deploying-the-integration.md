---
description: 'null'
seo-description: 'null'
seo-title: Implantação da integração
solution: Analytics
title: Implantação da integração
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: 56d27762320a752dff6ab4d9d763bbbf6e0deff5

---


# Implantação da integração{#deploying-the-integration}

A implantação dessa integração é um processo simples que requer as seguintes ações:

## Conclua o Assistente de integração da Adobe{#completing-the-adobe-integration-wizard}

Etapas para concluir o assistente de integração na interface dos Conectores de dados.

1. Navegue até a área Conectores de dados (anteriormente Genesis) na Adobe Experience Cloud.
1. Inicie o assistente de integração ContactLab.
1. Escolha o Conjunto de relatórios desejado e forneça um nome para a integração.
1. Configure the following items:

   | Item | Descrição |
   |---|---|
   | Endereço de email | O endereço de email do contato principal |
   | Descrição | (Opcional) Descrição para esta configuração de integração |

1. Configure os seguintes itens de Mapeamentos **[!UICONTROL de]** variável:

   | Item | Descrição |
   |---|---|
   | ID do link | Selecione uma eVar para coletar IDs de links em tempo real. |
   | Message ID | Selecione uma eVar para coletar IDs de mensagem em tempo real. |
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
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to ContactLab in daily remarketing segments.
   1. Rename calculated metrics as needed.
   1. Configure se você coletará IDs atualizando manualmente seu código de coleta do Analytics ou usando a solução automatizada. If you select Automated Solution, you must include the parameters that are used in email links to pass ID’s.****
1. Review all configuration items and click Activate Now.****

## Verify the Integration{#verifying-the-integration}

View your ContactLab integration setup within the Adobe Experience Cloud

1. View the integration activity log.
   1. In the Adobe Experience Cloud, navigate to Support &gt; Integration Activity Log.********

      ![](assets/integration_activity_log.png)

   1. Look for entries like Classification Data imported successfully, Metrics Data imported successfully, and Metric Data exported successfully. ************ Essas entradas devem aparecer dentro de 1 dia após a implantação bem-sucedida.
1. View your reporting data within Adobe Analytics.
   1. Navigate to Custom Conversion &gt; Custom Conversion 1-10 &gt; Message ID Reports.************

      ![](assets/reporting.png)

   1. Look for ContactLab reporting. This data should appear within 24-48 hours of successful deployment.