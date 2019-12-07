---
description: 'null'
title: Implantação da integração
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implantação da integração{#deploying-the-integration}

A implantação dessa integração é um processo simples que consiste em concluir o Assistente de integração da Adobe e verificar a integração.

## Concluindo o Assistente de integração da Adobe{#completing-the-adobe-integration-wizard}

Etapas para concluir o assistente de integração na interface dos Conectores de dados.

1. Navegue até a área Conectores de dados (anteriormente Genesis) na Adobe Experience Cloud.
1. Inicie o assistente de integração de Sinal dinâmico.
1. Escolha o Conjunto de relatórios desejado e forneça um nome para a integração.
1. Configure os seguintes itens:

   | Item | Descrição |
   |---|---|
   | Endereço de email | O endereço de email do contato principal. |
   | Descrição | (Opcional) Descrição para esta configuração de integração. |
   | ID da comunidade | Você pode obter essa ID do seu representante de Sinal dinâmico. |

1. Configure os seguintes itens de Mapeamentos **[!UICONTROL de]** variável:

   | Item | Descrição |
   |---|---|
   | Código de Acompanhamento | Selecione uma variável eVar disponível no conjunto de relatórios. |

1. Revise as classificações que serão criadas para essa integração.
1. Marque a caixa para criar o painel de integração do Sinal dinâmico (opcional, mas altamente recomendado).
1. Revise todos os itens de configuração e clique em **[!UICONTROL Ativar agora]**.
1. **Importante**: Depois de concluir o assistente, você deve notificar seu representante de Sinal dinâmico para que ele possa ativar a integração na plataforma VoiceStorm.

## Verificação da integração{#verifying-the-integration}

Etapas para exibir a configuração da integração do Dynamic Signal VoiceStorm na Adobe Experience Cloud

1. Veja a configuração da integração do Sinal dinâmico no registro de atividades de integração.
   1. Na Adobe Experience Cloud, navegue até **[!UICONTROL Suporte]** &gt; Log **[!UICONTROL de atividades de]** integração.

      ![](assets/integration_activity_log.png)

   1. Procure entradas como Dados de **[!UICONTROL classificação importados com êxito]**. Essas entradas devem aparecer dentro de 24 horas após a implantação bem-sucedida.
1. Revise seus relatórios de Sinal dinâmico no Adobe Analytics usando o Painel que foi criado automaticamente para você usando o assistente de integração da Adobe (Etapa 7). Como alternativa, você pode navegar até o relatório de Sinal dinâmico na estrutura de menu do Adobe Analytics - consulte as seguintes capturas de tela.

   **Observação**:Esses dados devem aparecer entre 24 e 48 horas após a implantação bem-sucedida.

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
