---
description: Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.
title: Habilitar o Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: ht
source-wordcount: '622'
ht-degree: 100%

---


# Ativar e habilitar o Activity Map

Explica as etapas que o Administrador do Analytics precisa completar para ativar a coleta de links e o download do usuário no Activity Map.

## Etapa 1. Ativar o Activity Map {#update_code}

O módulo Activity Map faz parte do AppMeasurement.js, das tags da Adobe Experience Platform e do SDK da Web (alloy.js). Os dados do Activity Map não podem ser coletados a menos que você atualize para o **SDK da Web versão 2.15.0** ou superior, para a **Extensão de tags do Adobe Analytics versão 1.90** ou superior, ou para o **AppMeasurement versão 1.6** ou superior.

+++SDK da Web (extensão de tags da Adobe Experience Platform)

1. Nas tags da Adobe Experience Platform, navegue até a propriedade para a qual você está implementando o Analytics. Em [!UICONTROL Extensões] -> [!UICONTROL SDK da Web da Adobe Experience Platform], selecione **[!UICONTROL Habilitar a coleta de dados de cliques]**, conforme destacado abaixo.
1. Crie a biblioteca com as alterações.
1. Publique a biblioteca na produção.

![](assets/web_sdk.png)

**Validação**

Interaja com chamadas usando a guia Rede do Developer Console:

1. Carregue o script Development Launch no site.
1. Ao clicar em Elementos, procure por “/ee” na guia Rede

   ![](assets/validation1.png)

Adobe Experience Platform Debugger:

1. Baixe e instale o [Adobe Experience Platform Debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. Acesse [!UICONTROL Logs] > [!UICONTROL Edge] > [!UICONTROL Conectar ao Edge].

   ![](assets/validation2.jpg)

**Perguntas frequentes**

* **A chamada interativa não está sendo acionada na guia Rede.**
Na coleta de dados de cliques em uma chamada de coleta, é necessário filtrar com “/ee” ou “collect”?

* **O conteúdo não é exibido para a chamada de coleta.**
A chamada de coleta foi desenvolvida de modo que o rastreamento não afete a navegação para outros sites, portanto, o recurso de descarregamento de documentos é aplicável nas chamadas de coleta. Isso não afetará a coleta de dados, mas se for necessário validar na página, adicione target = “_blank” ao respectivo elemento. Em seguida, o link é aberto em uma nova guia.

* **Como ignorar a coleção de PII?**
Adicione as respectivas condições in&lt;&lt; on before link click send callback>> e retorne como “falso” para ignorar esses valores. [Saiba mais](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR)

  Código de exemplo:

  ![](assets/sample-code.png)

+++

+++Implementação manual do SDK da Web

Consulte [Rastrear links](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) para obter informações sobre como implementar o rastreamento de link e habilitar o Activity Map capturando o `region` do elemento de HTML clicado.

>[!NOTE]
>
>Habilitar o rastreamento de link com o SDK da Web atualmente envia eventos de link quando um cliente navega de uma página para outra. Isso é diferente de como o AppMeasurement funciona e pode resultar no envio de ocorrências faturáveis adicionais à Adobe.

+++

+++Extensão do Analytics (tags da Adobe Experience Platform)

Nas tags da Adobe Experience Platform, navegue até a propriedade para a qual você está implementando o Analytics. Na caixa de diálogo [!UICONTROL Instalar extensão], selecione **[!UICONTROL Usar Activity Map]**.

![](assets/aa_extension.png)

+++

+++AppMeasurement

1. Baixe a biblioteca Javascript mais recente para o AppMeasurement.
Acesse **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Todos os(as) admins]** > **[!UICONTROL Gerenciador de código]**.
1. Implemente-a seguindo [estas instruções](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=pt-BR).

+++

## Etapa 2. Ativar relatórios do Activity Map {#enable}

É preciso habilitar os relatórios do Activity Map no nível de conjunto de relatórios.

1. Faça logon no Adobe Analytics e acesse  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar configurações]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Relatórios do Activity Map]**.

1. O Activity Map coleta os dados do link nos Relatórios do Activity Map. Para ocorrer a ativação, você deve primeiro ativar as variáveis, &#x200B;&#x200B;clicando em **[!UICONTROL Ativar os Relatórios do Activity Map]**.

   Essa etapa adiciona todas as dimensões do Analytics necessárias para coletar os dados.

   ![](assets/enable.png)

1. Após cerca de uma hora, verifique o [Relatório de página do Activity Map](/help/analyze/activity-map/activitymap-reporting-analytics.md), que mostra todas as páginas onde os usuários clicaram em um link.

## Etapa 3. Adicionar usuários ao perfil de produto [!UICONTROL Acesso ao Activity Map] {#add_users}

1. Clique em **[!UICONTROL Adicionar usuários ao grupo]**.

   Isso levará você à página de perfil do produto no [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. Se você não criou um perfil de produto [!UICONTROL Acesso ao Activity Map], crie-o agora. Os itens de permissão necessários para este perfil são [!UICONTROL Ferramentas do Analytics] > [!UICONTROL Activity Map] e [!UICONTROL Ferramentas do Analytics] > [!UICONTROL Publicação de segmento].

1. Adicione usuários a esse perfil de produto. Isso permite que os usuários baixem o Activity Map em **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Ferramentas]** > **[!UICONTROL ActivityMap]**.

