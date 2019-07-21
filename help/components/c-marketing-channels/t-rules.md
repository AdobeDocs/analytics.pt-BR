---
description: Crie regras de processamento do Canal de marketing. Elas determinam se uma ocorrência de visitante atende aos critérios atribuídos a um canal.
seo-description: Crie regras de processamento do Canal de marketing. Elas determinam se uma ocorrência de visitante atende aos critérios atribuídos a um canal.
seo-title: Criar regras de processamento de Canal de marketing
solution: Analytics
subtopic: Canais de marketing
title: Criar regras de processamento de Canal de marketing
topic: Reports and Analytics
uuid: 0 e 47634 f -3 c 69-46 db -8 af 4-8 d 0 b 3 d 15 f 7 a 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Criar regras de processamento de Canal de marketing

Crie regras de processamento do Canal de marketing. Elas determinam se uma ocorrência de visitante atende aos critérios atribuídos a um canal.

Este procedimento utiliza uma regra de email como exemplo. O exemplo assume que você adicionou um canal de email à lista de canais na página do Gerenciador de canal marketing.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Selecione um conjunto de relatórios.

   Se seu conjunto de ferramentas de relatório não tem canais definidos, a página [!UICONTROL Configuração inicial automática] é exibida.

   Consulte [Executar a configuração automática](/help/components/c-marketing-channels/c-channel-autosetup.md).

1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Resultado da etapa](assets/marketing_channel_rules.png)

1. Em **Adicionar novo conjunto de regras**, selecione **[!UICONTROL Email]**.

   Ao fazer isso, você não está selecionando o canal, mas um modelo que preenche a regra com alguns dos parâmetros necessários.

   ![Resultado da etapa](assets/example_email.png)

   Use lógica booleana (instruções if/then) para configurar uma regra. Por exemplo, em uma regra de canal de email, forneça as configurações ou informações destacadas na seguinte instrução da regra:

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   In this example, *`<value>`* is the query string parameter that you use for your email campaign, such as *`eml`*.
1. Para continuar criando regras, clique em **[!UICONTROL Adicionar regra]**.
1. Para criar prioridades de regras, arraste-as e solte-as na posição desejada.
1. Clique em **[!UICONTROL Salvar.]**

>[!MORE_LIKE_THIS]
>
>* [Perguntas mais frequentes e exemplos](/help/components/c-marketing-channels/c-faq.md)

