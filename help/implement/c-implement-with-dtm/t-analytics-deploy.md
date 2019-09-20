---
description: Crie uma ferramenta Adobe Analytics para implantação usando o Dynamic Tag Management. Este procedimento descreve uma implementação manual (herdada).
keywords: Dynamic Tag Management
seo-description: Crie uma ferramenta Adobe Analytics para implantação usando o Dynamic Tag Management. Este procedimento descreve uma implementação manual (herdada).
seo-title: Implementação manual do Adobe Analytics (herdado)
solution: Experience Cloud,Analytics,Target,Gerenciamento dinâmico de tags
title: Implementação manual do Adobe Analytics (herdado)
uuid: d3ad2035-393d-4a77-81f6-e749ee717c09
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Implementação manual do Adobe Analytics (herdado)

Create an Adobe Analytics tool for deployment using [!UICONTROL Dynamic Tag Management]. Este procedimento descreve uma implementação manual (herdada).

Para obter informações sobre o gerenciamento da implementação automática, consulte [Adicionar a ferramenta Adobe Analytics](../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8).

Se você deseja alterar uma configuração manual para automática, edite uma ferramenta e clique em **[!UICONTROL Habilitar a configuração automática]**.

1. Baixe o código de medição do Analytics:
   1. No Analytics, clique em **[!UICONTROL Admin]** &gt; Gerenciador **[!UICONTROL de código]**.
   1. Click **[!UICONTROL JavaScript (new)]** to download the code locally.
1. No Gerenciamento dinâmico de tags, [crie uma propriedade](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123)da Web.

   ![](assets/dtm-property.png)

   Depois de ser criada, a propriedade da Web fica disponível para edição na guia [!UICONTROL Propriedades da Web] no [!UICONTROL Painel]. Não é necessário ativar a propriedade da Web.

1. Adicione uma ferramenta do Analytics à propriedade:
   1. On the **[!UICONTROL Web Properties]** tab, click the property.
   1. On the **[!UICONTROL Overview]** tab, click **[!UICONTROL Add a Tool]**.
   1. From the **[!UICONTROL Tool Type]** menu, select **[!UICONTROL Adobe Analytics]**.

      ![](assets/dtm-add-analytics-tool.png)

   1. Configure os seguintes campos:

      | Elemento | Descrição |
      |---|---|
      | Tipo de ferramenta | A solução da Experience Cloud, como o Analytics, o Target, o Social, etc. |
      | Nome da ferramenta | O nome da ferramenta. Esse nome é exibido na guia [!UICONTROL Visão geral] em [!UICONTROL Ferramentas instaladas]. |
      | ID da conta de produção | Um número para a conta de produção para a coleção de dados. O Dynamic Tag Management instala automaticamente a conta correta no ambiente de produção e preparação. |
      | ID da conta de armazenamento temporário | Um número usado no ambiente de desenvolvimento e de teste. Uma conta de armazenamento temporário mantém os dados dos testes separados da produção. |

1. Clique em **[!UICONTROL Criar ferramenta]**.

   A ferramenta instalada é exibida na guia [!UICONTROL Visão geral].

1. To configure the code, click **[!UICONTROL Settings]** ![](assets/settings_gear.png).

   No mínimo, clique em **[!UICONTROL Cookies]e configure o seu servidor de rastreamento e o servidor de rastreamento do SSL.**

1. Clique em **[!UICONTROL Geral]** e [insira o código](../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658)principal do AppMeasurement.
1. Defina uma regra [de carregamento de](../../implement/c-implement-with-dtm/c-rules/t-rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB) página para coletar [!DNL Analytics]dados.

   Agora, você está pronto para definir as regras para coletar os dados do Analytics. Talvez você queira definir alguns elementos de dados primeiro. Os elementos de dados permitem extrair os dados da página que pode ser usada para configurar a regra. Para iniciar, você pode definir uma regra de carregamento de página que não tenha condições de coletar dados do [!DNL Analytics] em cada página.
1. [Adicione o código do cabeçalho e do rodapé](../../implement/c-implement-with-dtm/c-headers-footers/t-header-footer-code.md#task_43C8DD699A514638B0620775C06423E5) na guia Incorporado.

   Para o armazenamento temporário, você pode deixar a opção de hospedagem padrão da Amazon. É possível alterá-la se necessário antes do lançamento da produção.
1. (Optional) Click **[!UICONTROL Settings]** ![](assets/settings_gear.png) on the Options tab, and configure the Adobe Analytics code.

   >[!NOTE]
   >
   >The settings on the [!UICONTROL Adobe Analytics] page (General, Cookies, and so on) override settings in your `s_code`. Se essas configurações existem no `s_code`, não é necessário repeti-las aqui.

