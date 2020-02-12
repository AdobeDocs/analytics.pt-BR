---
title: Criar regras de processamento de Canal de marketing
description: Crie regras de processamento do Canal de marketing. Elas determinam se uma ocorrência de visitante atende aos critérios atribuídos a um canal.
translation-type: tm+mt
source-git-commit: ea4d9e6c9396032fe323de594cb43eecbf97aa15

---


# Criar regras de processamento de Canal de marketing

Crie regras de processamento do Canal de marketing. Elas determinam se uma ocorrência de visitante atende aos critérios atribuídos a um canal.

Este procedimento utiliza uma regra de email como exemplo. O exemplo assume que você adicionou um canal de email à lista de canais na página do Gerenciador de canal marketing.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Selecione um conjunto de relatórios.

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md).

1. Clique em **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Resultado da etapa](assets/marketing_channel_rules.png)

1. No **[!UICONTROL Add New Rule Set]** menu, selecione **[!UICONTROL Email]**.

   Ao fazer isso, você não está selecionando o canal, mas um modelo que preenche a regra com alguns dos parâmetros necessários.

   ![Resultado da etapa](assets/example_email.png)

   Use lógica booleana (instruções if/then) para configurar uma regra. Por exemplo, em uma regra de canal de email, forneça as configurações ou informações destacadas na seguinte instrução da regra:

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   Nesse exemplo, *`<value>`* é o parâmetro de sequência de caracteres de consulta utilizado para a campanha de email como, por exemplo, *`eml`*.
1. Para continuar criando regras, clique em **[!UICONTROL Add Rule]**.
1. Para criar prioridades de regras, arraste-as e solte-as na posição desejada.
1. Clique em **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [Perguntas mais frequentes e exemplos](/help/components/c-marketing-channels/mc-faq/c-faq.md)

