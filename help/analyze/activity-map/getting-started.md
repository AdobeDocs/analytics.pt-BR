---
title: Introdução ao Activity Map
description: Introdução ao uso da sobreposição de Activity Map e das dimensões.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 0%

---

# Introdução ao Activity Map

O Activity Map no Adobe Analytics inclui quatro elementos principais:

* **Configuração do conjunto de relatórios**: você deve habilitar o Activity Map nas configurações do conjunto de relatórios. Quando ativado, o conjunto de relatórios cria várias variáveis reservadas para dimensões e métricas Activity Map.
* **Implementação**: coletar dados de Activity Map no site ou na propriedade. Personalizar como os dados são coletados pode melhorar a qualidade e a experiência dos relatórios.
* **Dimensões e métricas do Workspace**: quando a implementação é configurada corretamente, você pode usar dimensões e métricas do Activity Map no Analysis Workspace.
* **Sobreposição**: o Adobe oferece uma extensão de navegador para exibir dados de Activity Map no contexto do site.

## Ativar configuração do conjunto de relatórios

Um conjunto de relatórios deve ter o relatório de Activity Map habilitado para que você possa começar a coletar dados. Se sua implementação enviar dados de Activity Map para um conjunto de relatórios sem o relatório de Activity Map habilitado, os dados de Activity Map não serão incluídos na ocorrência.

**[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar configurações]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Relatórios de Activity Map]** > **[!UICONTROL Habilitar Relatórios de Activity Map]**

Habilitar relatórios de Activity Map cria várias variáveis reservadas de back-end. Consulte [Relatórios de Activity Map](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) no guia de administração do Adobe Analytics para obter mais informações.

## Instalação do código

Sua implementação deve ser configurada corretamente para enviar dados de Activity Map para o Adobe.

+++Extensão de tag do SDK da Web

A coleta de dados do Activity Map requer a extensão **[!UICONTROL Adobe Experience Platform Web SDK]** v2.23 ou posterior. As versões de extensão até a v2.16 têm suporte limitado. Essas versões de extensão anteriores enviam dados de Activity Map em um evento separado do restante dos dados. Esse evento extra aumenta o número de ocorrências enviadas para o Adobe Analytics ou Adobe Experience Platform.

A definição de configuração **[!UICONTROL Coleta de dados de cliques]** lida com a coleta de dados de Activity Map e geralmente é habilitada por padrão. Você pode verificar se está ativado nas configurações da extensão:

1. Faça logon em [experience.adobe.com](https://experience.adobe.com)
1. Selecione **[!UICONTROL Coleção de dados]** no menu de acesso rápido ou no seletor de produtos no canto superior direito.
1. Selecione **[!UICONTROL Tags]** no menu de navegação esquerdo.
1. Selecione a tag desejada para editar.
1. Selecione **[!UICONTROL Extensões]** no menu de navegação esquerdo.
1. Selecione **[!UICONTROL Adobe Experience Platform Web SDK]** na lista de extensões instaladas e selecione **[!UICONTROL Configurar]** à direita.
1. Localize a seção denominada [!UICONTROL Coleta de Dados] e verifique se a caixa de seleção **[!UICONTROL Habilitar coleta de dados de cliques]** está habilitada.
1. Selecione **[!UICONTROL Salvar]**.
1. Se necessário, crie as alterações em uma biblioteca e publique as alterações na produção.

Consulte [Configurar a extensão de tag do SDK da Web](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) para obter mais informações.

+++

+++Biblioteca JavaScript do SDK da Web (`alloy.js`)

A coleção de dados do Activity Map exige a biblioteca JavaScript do SDK da Web v2.20 ou posterior. As versões de biblioteca até a v2.15 têm suporte limitado. Essas versões anteriores da biblioteca enviam dados de Activity Map em um evento separado do restante dos dados. Esse evento extra aumenta o número de ocorrências enviadas para o Adobe Analytics ou Adobe Experience Platform.

A variável de configuração [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) do SDK da Web manipula a coleta automática de dados Activity Map. Ela é ativada por padrão, a menos que explicitamente desativada.

```js
alloy("configure", {
  "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
  "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg",
  "clickCollectionEnabled": true
});
```

+++

+++Extensão de tag do Adobe Analytics

A definição de configuração **[!UICONTROL Usar Activity Map]** lida com a coleta de dados Activity Map e é normalmente habilitada por padrão. Ela está disponível para todas as extensões de tag v1.9.0 ou posterior. Você pode verificar se está ativado nas configurações da extensão:

1. Faça logon em [experience.adobe.com](https://experience.adobe.com)
1. Selecione **[!UICONTROL Coleção de dados]** no menu de acesso rápido ou no seletor de produtos no canto superior direito.
1. Selecione **[!UICONTROL Tags]** no menu de navegação esquerdo.
1. Selecione a tag desejada para editar.
1. Selecione **[!UICONTROL Extensões]** no menu de navegação esquerdo.
1. Selecione **[!UICONTROL Adobe Analytics]** na lista de extensões instaladas e selecione **[!UICONTROL Configurar]** à direita.
1. Verifique se a caixa de seleção **[!UICONTROL Usar Activity Map]** está habilitada.
1. Selecione **[!UICONTROL Salvar]**.
1. Se necessário, crie as alterações em uma biblioteca e publique as alterações na produção.

Consulte a [visão geral da extensão do Adobe Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) para obter mais informações.

+++

+++Biblioteca JavaScript do Adobe Analytics (`AppMeasurement.js`)

O módulo Activity Map lida com a coleta de dados Activity Map e está incluído em todas as bibliotecas de AppMeasurements v1.6 ou mais recentes. Você pode inspecionar o arquivo `AppMeasurement.js` para verificar se ele está incluído.

1. Navegue até a [versão mais recente do Adobe Analytics AppMeasurement](https://github.com/adobe/appmeasurement/releases/latest) no GitHub.
1. Baixe o arquivo de biblioteca de AppMeasurements compactado e abra `AppMeasurement.js` contido nele.
1. O módulo Activity Map está incluído próximo à parte superior desse arquivo. Certifique-se de que esse módulo esteja incluído na biblioteca do AppMeasurement que seu site usa.

+++

## Dimensões disponíveis

Quando o Activity Map estiver ativado para o conjunto de relatórios e a implementação, você poderá começar a usar as seguintes dimensões no Analysis Workspace:

* [[!UICONTROL Activity Map Link]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Região do Activity Map]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Map Página]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Link Por Região] Do Activity Map](/help/components/dimensions/activity-map-link-by-region.md)

## Baixar e instalar a extensão ou o complemento do navegador

Além das dimensões disponíveis no Analysis Workspace, você também pode visualizar dados do Activity Map como uma sobreposição em seu site. Para visualizar essa sobreposição, baixe e instale a extensão ou o complemento do navegador Activity Map.

**[!UICONTROL Ferramentas]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Baixar Activity Map]**

Esse link direciona você para a extensão suportada do navegador ou o marketplace complementar, onde é possível instalá-lo. Depois de instalada, a extensão ou o complemento é exibido na parte superior direita do navegador, onde é possível entrar e habilitar a sobreposição.
