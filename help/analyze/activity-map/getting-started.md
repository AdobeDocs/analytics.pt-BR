---
title: Introdução ao Activity Map
description: Introdução ao uso da sobreposição e das dimensões do Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# Introdução ao Activity Map

O Activity Map no Adobe Analytics inclui quatro elementos principais:

* **Configuração do conjunto de relatórios**: você deve habilitar o Activity Map nas configurações do conjunto de relatórios. Quando ativado, o conjunto de relatórios cria várias variáveis reservadas para dimensões e métricas do Activity Map.
* **Implementação**: coletar dados do Activity Map no site ou na propriedade. Personalizar como os dados são coletados pode melhorar a qualidade e a experiência dos relatórios.
* **Dimensões e métricas do Workspace**: quando a implementação é configurada corretamente, você pode usar dimensões e métricas do Activity Map no Analysis Workspace.
* **Sobreposição**: o Adobe oferece uma extensão de navegador para exibir dados do Activity Map no contexto do site.

## Ativar configuração do conjunto de relatórios

Um conjunto de relatórios deve ter os relatórios do Activity Map ativados antes de você começar a coletar dados. Se sua implementação enviar dados do Activity Map para um conjunto de relatórios sem os relatórios do Activity Map ativados, os dados do Activity Map não serão incluídos na ocorrência.

**[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar configurações]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Relatórios do Activity Map]** > **[!UICONTROL Habilitar Relatórios do Activity Map]**

Habilitar relatórios do Activity Map cria várias variáveis reservadas de backend. Consulte [Relatórios do Activity Map](/help/admin/tools/manage-rs/edit-settings/activity-map.md) no guia de administração do Adobe Analytics para obter mais informações.

## Instalação do código

Sua implementação deve estar configurada corretamente para enviar dados do Activity Map para o Adobe.

+++Extensão da tag do SDK da web

A coleta de dados do Activity Map exige a extensão do **[!UICONTROL Adobe Experience Platform Web SDK]** v2.23 ou posterior. As versões de extensão até a v2.16 têm suporte limitado. Essas versões de extensão anteriores enviam dados do Activity Map em um evento separado do restante dos dados. Esse evento extra aumenta o número de ocorrências enviadas para o Adobe Analytics ou Adobe Experience Platform.

A definição de configuração **[!UICONTROL Coleta de dados de cliques]** lida com a coleta de dados do Activity Map e é normalmente habilitada por padrão. Você pode verificar se está ativado nas configurações da extensão:

1. Faça logon em [experience.adobe.com](https://experience.adobe.com)
1. Selecione **[!UICONTROL Coleção de dados]** no menu de acesso rápido ou no seletor de produtos no canto superior direito.
1. Selecione **[!UICONTROL Tags]** no menu de navegação esquerdo.
1. Selecione a tag desejada para editar.
1. Selecione **[!UICONTROL Extensões]** no menu de navegação esquerdo.
1. Selecione **[!UICONTROL Adobe Experience Platform Web SDK]** na lista de extensões instaladas e selecione **[!UICONTROL Configurar]** à direita.
1. Localize a seção denominada [!UICONTROL Coleta de Dados] e verifique se a caixa de seleção **[!UICONTROL Habilitar coleta de dados de cliques]** está habilitada.
1. Selecione **[!UICONTROL Salvar]**.
1. Se necessário, crie as alterações em uma biblioteca e publique as alterações na produção.

Consulte [Configurar a extensão de marca do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) para obter mais informações.

+++

+++Biblioteca JavaScript do Web SDK (`alloy.js`)

A coleta de dados do Activity Map exige a biblioteca Web SDK JavaScript v2.20 ou posterior. As versões de biblioteca até a v2.15 têm suporte limitado. Essas versões anteriores da biblioteca enviam dados do Activity Map em um evento separado do restante dos dados. Esse evento extra aumenta o número de ocorrências enviadas para o Adobe Analytics ou Adobe Experience Platform.

A variável de configuração [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) do Web SDK manipula a coleta automática de dados do Activity Map. Ela é ativada por padrão, a menos que explicitamente desativada.

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Extensão de tag do Adobe Analytics

A definição de configuração **[!UICONTROL Usar Activity Map]** lida com a coleta de dados do Activity Map e é normalmente habilitada por padrão. Ela está disponível para todas as extensões de tag v1.9.0 ou posterior. Você pode verificar se está ativado nas configurações da extensão:

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

O módulo Activity Map lida com a coleção de dados do Activity Map e está incluído em todas as bibliotecas AppMeasurement v1.6 ou posterior. Você pode inspecionar o arquivo `AppMeasurement.js` para verificar se ele está incluído.

1. Navegue até a [versão mais recente do Adobe Analytics AppMeasurement](https://github.com/adobe/appmeasurement/releases/latest) no GitHub.
1. Baixe o arquivo de biblioteca AppMeasurement compactado e abra `AppMeasurement.js` contido nele.
1. O módulo Activity Map está incluído próximo à parte superior desse arquivo. Certifique-se de que esse módulo esteja incluído na biblioteca do AppMeasurement que seu site usa.

+++

## Dimensões disponíveis

Quando a Activity Map estiver ativada para o conjunto de relatórios e a implementação, você poderá começar a usar as seguintes dimensões no Analysis Workspace:

* [[!UICONTROL Link do Activity Map]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Região do Activity Map]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Página do Activity Map]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Link Do Activity Map Por Região]](/help/components/dimensions/activity-map-link-by-region.md)

## Baixar e instalar a extensão ou o complemento do navegador

Além das dimensões disponíveis no Analysis Workspace, você também pode visualizar os dados do Activity Map como uma sobreposição em seu site. Para visualizar essa sobreposição, baixe e instale a extensão ou o complemento do navegador Activity Map.

**[!UICONTROL Ferramentas]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Baixar Activity Map]**

Esse link direciona você para a extensão suportada do navegador ou o marketplace complementar, onde é possível instalá-lo. Depois de instalada, a extensão ou o complemento é exibido na parte superior direita do navegador, onde é possível entrar e habilitar a sobreposição.
