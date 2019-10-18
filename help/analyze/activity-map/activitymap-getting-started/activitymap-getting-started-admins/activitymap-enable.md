---
description: Explica as etapas que o Administrador do Analytics precisa concluir para habilitar a coleta de links e o download do usuário do [!DNL Activity Map].
seo-description: Explica as etapas que o Administrador do Analytics precisa concluir para habilitar a coleta de links e o download do usuário do [!DNL Activity Map].
seo-title: Habilitar [!DNL Activity Map]
solution: Analytics
title: Habilitar [!DNL Activity Map]
topic: Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# Ativar [!DNL Activity Map]{#enable-activity-map}

Explains the steps the Analytics Admin needs to complete to enable [!DNL Activity Map] link collection and user download.

## Etapa 1. Atualizar o código AppMeasurement (Javascript) para v1.6 (ou posterior) {#section_5D1586289DF2489289B1B6C1C80C300D}

The [!DNL Activity Map] module is part of the AppMeasurement.js file (located at the top of the file). The AppMeasurement library will load the [!DNL Activity Map] module when instantiated.

[!DNL Activity Map]Os dados do não podem ser coletados, a menos que você atualize para essa versão (ou posterior) do AppMeasurement.

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   Incluímos alguns [códigos de implementação de exemplo](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734) para ajudar a visualizar as alterações feitas no código, incluindo o módulo [!DNL Activity Map]

1. Validar a implementação:

   1. Ao clicar em um elemento clicável, os dados serão armazenados em um cookie chamado s_sq.
   1. The [!DNL Activity Map] data can be seen in the query-string on the tracking call. Por exemplo:

      ```
      …&c.&a.&[!DNL Activity Map].&link=My%20Link&region=My%20Region&page=My%20Page&.[!DNL Activity Map]&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL [!DNL Activity Map]Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## Etapa 2: Ativar [!DNL Activity Map] relatórios {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

First, you need to enable [!DNL Activity Map] reports at a report-suite level.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt;[!DNL Activity Map]]** &gt; **[!UICONTROL [!DNL Activity Map]Reporting]** .
1. [!DNL Activity Map] coleta os dados do link nos [!DNL Activity Map] relatórios. For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable[!DNL Activity Map]Reports]**.

   Essa etapa adiciona todas as dimensões do Analytics necessárias para coletar os dados.

1. After about an hour, check the [[!DNL Activity Map] Page report](/help/analyze/activity-map/activitymap-reporting-analytics.md), which shows all the pages where users clicked on a link.

## Etapa 3. Add users to [!DNL Activity Map] access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Clique em **[!UICONTROL Adicionar usuários ao grupo]**.

   Isso vai redirecionar você até a página de gerenciamento de grupos no Admin Console.

1. [Adicione usuários a esse grupo](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) e **[!UICONTROL Salve o grupo]**.

1. This allow your Admin users to download [!DNL Activity Map] from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  Se você quiser que usuários não administradores baixem o [!DNL Activity Map], é necessário criar um novo grupo de usuários que forneça permissão para <span class="uicontrol"> Ferramentas </span> &gt; Instalação <span class="uicontrol"> herdada do ClickMap </span>. Você pode adicionar usuários não administradores a esse grupo. Este nível de permissão combinado com o [!DNL Activity Map] Access fornecerá permissões abrangentes para baixar e usar a ferramenta. 
</note>
