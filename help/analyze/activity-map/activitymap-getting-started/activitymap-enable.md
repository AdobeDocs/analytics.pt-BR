---
description: Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.
title: Habilitar o Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: ae1c2ff1987e2fe5d147bfe74874b53492d48b5e
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 28%

---


# Ativar e ativar o Activity Map

Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.

## Etapa 1. Ativar Activity Map {#update_code}

O módulo Activity Map faz parte do AppMeasurement.js, das tags Adobe Experience Platform e do SDK da Web (alloy.js). Os dados de Activity Map não podem ser coletados a menos que você atualize para **Web SDK versão 2.15.0** ou superior, ou **Extensão de tags do Adobe Analytics v1.90** ou superior, ou **AppMeasurement versão 1.6** ou superior.

+++SDK da Web (extensão de tags do Adobe Experience Platform)

1. Nas tags do Adobe Experience Platform, navegue até a propriedade para a qual você está implementando o Analytics. Em [!UICONTROL Extensões] -> [!UICONTROL Adobe Experience Platform Web SDK], selecione **[!UICONTROL Ativar a coleta de dados de cliques]** como destacado abaixo.
1. Crie a biblioteca com as alterações.
1. Publique a Biblioteca para produção.

![](assets/web_sdk.png)

**Validação**

Interaja chamadas usando a guia Rede do Console do desenvolvedor:

1. Carregue o script do Development Launch no site.
1. Ao clicar em Elementos, procure por &quot;/ee&quot; na guia Rede

   ![](assets/validation1.png)

Adobe Experience Platform Debugger:

1. Baixe e instale o [Adobe Experience Platform Debugger](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. Ir para [!UICONTROL Logs] > [!UICONTROL Edge] > [!UICONTROL Conectar ao Edge].

   ![](assets/validation2.jpg)

**Perguntas frequentes**

* **A chamada interativa não está sendo acionada na guia Rede.**
Na coleta de dados de cliques em uma chamada de coleta, precisamos filtrar com &quot;/ee&quot; ou &quot;coletar?&quot;

* **Não há Exibição de carga para a chamada de coleta.**
A chamada de coleta é projetada de modo que o rastreamento não afete a navegação para outros sites, portanto, o recurso de descarregamento de documento é aplicável para as chamadas de coleta. Isso não afetará sua coleta de dados, mas se for necessário validar na página, adicione target = &quot;_blank&quot; ao respectivo elemento. Em seguida, o link é aberto em uma nova guia.

* **Como ignorar a coleção de PII?**
Adicione as respectivas condições em&lt;&lt; on antes de clicar em link enviar retorno de chamada>> e retorne false para ignorar esses valores. [Saiba mais](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR)

  Código de exemplo:

  ![](assets/sample-code.png)

+++

+++Implementação manual do SDK da Web

Consulte [Rastrear links](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=pt-BR) para obter informações sobre como implementar o rastreamento de link e como habilitar o Activity Map capturando o `region` do elemento de HTML clicado.

>[!NOTE]
>
>Atualmente, a ativação do rastreamento de links com o SDK da Web envia eventos de link quando um cliente navega de uma página para outra. Isso é diferente do funcionamento do AppMeasurement e pode resultar no envio de ocorrências faturáveis adicionais à Adobe.

+++

Extensão +++Analytics (tags do Adobe Experience Platform)

Nas tags do Adobe Experience Platform, navegue até a propriedade para a qual você está implementando o Analytics. No [!UICONTROL Instalar extensão] , selecione **[!UICONTROL Usar Activity Map]**.

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. Baixe a biblioteca JavaScript mais recente para o AppMeasurement.
Ir para **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Gerenciador de código]**.
1. Implemente-a seguindo [estas instruções](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=pt-BR).

+++

## Etapa 2. Ativar relatórios do Activity Map {#enable}

Você precisa ativar os relatórios de Activity Map no nível de conjunto de relatórios.

1. Faça logon no Adobe Analytics e acesse  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar configurações]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Relatórios do Activity Map]**.

1. O Activity Map coleta os dados do link nos Relatórios do Activity Map. Para ocorrer a ativação, você deve primeiro ativar as variáveis, &#x200B;&#x200B;clicando em **[!UICONTROL Ativar os Relatórios do Activity Map]**.

   Essa etapa adiciona todas as dimensões do Analytics necessárias para coletar os dados.

   ![](assets/enable.png)

1. Após cerca de uma hora, verifique o [Relatório de página do Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), que mostra todas as páginas onde os usuários clicaram em um link.

## Etapa 3. Adicionar usuários ao [!UICONTROL Acesso ao Activity Map] perfil do produto {#add_users}

1. Clique em **[!UICONTROL Adicionar usuários ao grupo]**.

   Isso o levará à página de perfil do produto no [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. Se você não criou um [!UICONTROL Acesso ao Activity Map] perfil do produto, faça isso agora. Os itens de permissão necessários para este perfil são [!UICONTROL Ferramentas do Analytics] > [!UICONTROL Activity Map] e [!UICONTROL Ferramentas do Analytics] > [!UICONTROL Publicação de segmento].

1. Adicione usuários a esse perfil de produto. Isso permite que os usuários baixem o Activity Map de  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Ferramentas]** > **[!UICONTROL ActivityMap]** .

