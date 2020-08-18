---
description: Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.
title: Habilitar o Activity Map
topic: Activity map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: aea3b4448b61e8b1b217b4f74b0b80c9fbedd070
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 94%

---


# Habilitar o Activity Map {#enable-activity-map}

Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.

## Etapa 1. Atualizar o código AppMeasurement (Javascript) para v1.6 (ou posterior) {#section_5D1586289DF2489289B1B6C1C80C300D}

O módulo do Activity Map é parte do arquivo AppMeasurement.js (localizado na parte superior do arquivo). A biblioteca do AppMeasurement vai carregar o módulo do Activity Map, quando esse for instanciado.

Os dados do Activity Map não podem ser coletados, a menos que você atualize para essa versão (ou posterior) do AppMeasurement.

1. Baixe o código AppMeasurement mais recente (AppMeasurement_Javascript-1.6.zip), acessando **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de código]** e [implemente-o](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/js/overview.html).

   Incluímos alguns [códigos de implementação de exemplo](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) para ajudar a visualizar as alterações feitas no código, incluindo o módulo Activity Map.

1. Valide a implementação:

   1. Ao clicar em um elemento clicável, os dados serão armazenados em um cookie chamado s_sq.
   1. Os dados do Activity Map podem ser visualizados na cadeia de caracteres de consulta, na chamada de rastreamento. Por exemplo:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Detalhe o relatório por **[!UICONTROL Link do Activity Map por região]** para visualizar o link/região da página: ![](assets/am_breakdown.png){width=&quot;400px&quot;}

## Etapa 2. Ativar relatórios do Activity Map {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Primeiro, você precisa ativar os Relatórios do Activity Map a um nível de conjunto de relatórios.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Select report suite > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]** .
1. O Activity Map coleta os dados do link nos Relatórios do Activity Map. Para ocorrer a ativação, você deve primeiro ativar as variáveis, &#x200B;&#x200B;clicando em **[!UICONTROL Ativar os Relatórios do Activity Map]**.

   Essa etapa adiciona todas as dimensões do Analytics necessárias para coletar os dados.

1. Após cerca de uma hora, verifique o [Relatório de página do Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), que mostra todas as páginas onde os usuários clicaram em um link.

## Etapa 3. Adicionar usuários ao grupo de acesso do Activity Map {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Clique em **[!UICONTROL Adicionar usuários ao grupo]**.

   Isso vai redirecionar você até a página de gerenciamento de grupos no Admin Console.

1. [Adicione usuários a esse grupo](https://docs.adobe.com/content/help/pt-BR/analytics/admin/user-product-management/user-groups/groups.html) e **[!UICONTROL Salve o grupo]**.

1. Isso permite que os usuários Administradores baixem o Activity Map em **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Ferramentas]** > **[!UICONTROL Activity Map]**.

>[!NOTE]
>
>Se você quiser que usuários não administradores baixem o Activity Map, crie um novo grupo de usuários que forneça permissão de acesso a &quot;Ferramentas&quot; e &quot;Instalação herdada do ClickMap&quot;. Este nível de permissão, combinado ao Acesso ao Activity Map, fornece permissões as para baixar e usar a ferramenta.
