---
description: Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.
title: Habilitar o Activity Map
uuid: 30433319-d0e6-4977-951a-4492b356e1f2
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: d4caf0ddc5cf5402bfef94a64db1c00e1c725658
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 74%

---

# Habilitar o Activity Map{#enable-activity-map}

Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.

## Etapa 1. Atualizar o código de implementação {#section_5D1586289DF2489289B1B6C1C80C300D}

O módulo Activity Map faz parte do AppMeasurement.js e do SDK da Web (versão 2.15.0 ou superior).
A biblioteca de AppMeasurements ou o SDK da Web carregará o módulo Activity Map quando instanciado.

>[!NOTE]
>
>Os dados de Activity Map não podem ser coletados a menos que você atualize para **AppMeasurement** **versão 1.6** ou superior ou **SDK da Web** **versão 2.15.0** ou superior.


1. Baixe a biblioteca JavaScript mais recente dependendo se você está usando o AppMeasurement ou o SDK da Web.

   - **AppMeasurement** (AppMeasurement_Javascript-1.6.zip) acessando  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Gerenciador de código]** e [implementá-lo](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=pt-BR).

     Incluímos alguns [códigos de implementação de exemplo](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md) para ajudar a visualizar as alterações feitas no código, incluindo o módulo Activity Map.

   - **SDK da Web** (alloy.js). Consulte [Instalar o SDK - Opção 2: instalação da versão independente pré-criada](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=pt-BR#option-2%3A-installing-the-prebuilt-standalone-version) para obter mais informações. Certifique-se de usar a versão 2.15 ou posterior.

     Consulte [Rastrear links](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=pt-BR) para obter informações sobre como implementar o rastreamento de link e como ativar o Activity Mapping capturando o `region` do elemento de HTML clicado.

     >[!NOTE]
     >
     >Atualmente, ao habilitar o rastreamento de link com o SDK da Web, eventos de links são enviados quando um cliente navega de uma página para a próxima. Isso é diferente do funcionamento do AppMeasurement e pode resultar no envio de ocorrências faturáveis adicionais à Adobe.


1. Valide a implementação:

   1. Ao clicar em um elemento clicável, os dados serão armazenados em um cookie chamado s_sq.
   1. Os dados do Activity Map podem ser visualizados na cadeia de caracteres de consulta, na chamada de rastreamento. Por exemplo:

      ```
      …&c.&a.&Activity Map.&link=My%20Link&region=My%20Region&page=My%20Page&.Activity Map&.a&.c&...
      ```

1. Detalhe o relatório por **[!UICONTROL Link do Activity Map por região]** para visualizar o link/região da página:  ![](assets/am_breakdown.png){width="400px"}

## Etapa 2. Ativar relatórios do Activity Map {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

Primeiro, você precisa ativar os Relatórios do Activity Map a um nível de conjunto de relatórios.

1. Faça logon no Adobe Analytics e acesse  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar configurações]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Relatórios do Activity Map]**.
1. O Activity Map coleta os dados do link nos Relatórios do Activity Map. Para ocorrer a ativação, você deve primeiro ativar as variáveis, &#x200B;&#x200B;clicando em **[!UICONTROL Ativar os Relatórios do Activity Map]**.

   Essa etapa adiciona todas as dimensões do Analytics necessárias para coletar os dados.

1. Após cerca de uma hora, verifique o [Relatório de página do Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), que mostra todas as páginas onde os usuários clicaram em um link.

## Etapa 3. Adicionar usuários ao grupo de acesso do Activity Map {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Clique em **[!UICONTROL Adicionar usuários ao grupo]**.

   Isso vai redirecionar você até a página de gerenciamento de grupos no Admin Console.

1. [Adicione usuários a esse grupo](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=pt-BR) e **[!UICONTROL Salve o grupo]**.

1. Isso permite que os usuários Administradores baixem o Activity Map em **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Ferramentas]** > **[!UICONTROL Activity Map]**.

>[!NOTE]
>
>Se você quiser que usuários não administradores baixem o Activity Map, crie um novo grupo de usuários que forneça permissão de acesso a &quot;Ferramentas&quot; e &quot;Instalação herdada do ClickMap&quot;. Este nível de permissão, combinado ao Acesso ao Activity Map, fornece permissões as para baixar e usar a ferramenta.
