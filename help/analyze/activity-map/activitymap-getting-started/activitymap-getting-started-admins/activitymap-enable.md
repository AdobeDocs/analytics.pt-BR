---
description: Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.
seo-description: Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.
seo-title: Ativar Activity Map
solution: Analytics
title: Ativar Activity Map
topic: Activity Map
uuid: 30433319-d 0 e 6-4977-951 a -4492 b 356 e 1 f 2
translation-type: tm+mt
source-git-commit: 8f72f8cf086be0eade5616b074123a9f22e33347

---


# Enable Activity Map{#enable-activity-map}

Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.

## Etapa 1. Atualizar o código AppMeasurement (Javascript) para v1.6 (ou posterior) {#section_5D1586289DF2489289B1B6C1C80C300D}

O módulo do Activity Map é parte do arquivo AppMeasurement.js (localizado na parte superior do arquivo). A biblioteca do AppMeasurement vai carregar o módulo do Activity Map, quando esse for instanciado.

Os dados do Activity Map não podem ser coletados, a menos que você atualize para essa versão (ou posterior) do AppMeasurement.

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   Incluímos alguns [códigos de implementação de exemplo](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734) para ajudar a visualizar as alterações feitas no código, incluindo o módulo Activity Map.

1. Validar a implementação:

   1. Ao clicar em um elemento clicável, os dados serão armazenados em um cookie chamado s_sq.
   1. Os dados do Activity Map podem ser visualizados na cadeia de caracteres de consulta, na chamada de rastreamento. Por exemplo:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL Activity Map Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## Etapa 2: Enable Activity Map reports {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Primeiro, você precisa ativar os Relatórios do Activity Map a um nível de conjunto de relatórios.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt; Activity Map]** &gt; **[!UICONTROL Activity Map Reporting]** .
1. O Activity Map coleta os dados do link nos Relatórios do Activity Map. Para ocorrer a ativação, você deve primeiro ativar as variáveis, &#x200B;&#x200B;clicando em **[!UICONTROL Ativar os Relatórios do Activity Map]**.

   Essa etapa adiciona todas as dimensões do Analytics necessárias para coletar os dados.

1. Após cerca de uma hora, verifique o [Relatório de página do Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), que mostra todas as páginas onde os usuários clicaram em um link.

## Etapa 3. Add users to Activity Map access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Clique em **[!UICONTROL Adicionar usuários ao grupo]**.

   Isso vai redirecionar você até a página de gerenciamento de grupos no Admin Console.

1. [Adicione usuários a esse grupo](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) e **[!UICONTROL Salve o grupo]**.

1. This allow your Admin users to download Activity Map from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  If you want Non-Admin users to download Activity Map, you need to create a new user group that provides permission to 
 <span class="uicontrol"> Tools </span> &gt; 
 <span class="uicontrol"> Legacy ClickMap Installation </span>. Você pode adicionar usuários não Administradores a este grupo. Esse nível de permissão combinado com o Acesso ao Mapa de atividade fornecerá permissões abrangentes para baixar e usar a ferramenta. 
</note>
