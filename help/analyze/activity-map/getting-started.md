---
title: Introdução ao Activity Map
description: Introdução ao uso da sobreposição e das dimensões do Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
TQID: https://experienceleague.adobe.com/Wt30b3LTZWyzAQFOKqkqBdWH2Ifatq5FLp-Z0z7nktA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: af860ea2bf90f0f25bfb95b943d9ae11bf808028
workflow-type: tm+mt
source-wordcount: 933
ht-degree: 97%

---

# Introdução ao Activity Map

O Activity Map no Adobe Analytics compreende quatro elementos principais:

* **Configuração do conjunto de relatórios**: é necessário habilitar o Activity Map nas Configurações do conjunto de relatórios. Quando habilitado, o conjunto de relatórios cria diversas variáveis reservadas para dimensões e métricas do Activity Map.
* **Implementação**: coleta dados do Activity Map no site ou na propriedade. Personalizar como os dados são coletados pode melhorar a qualidade e a experiência dos relatórios.
* **Dimensões e métricas do Workspace**: quando a implementação é configurada corretamente, é possível usar dimensões e métricas do Activity Map no Analysis Workspace.
* **Sobreposição**: a Adobe oferece uma extensão de navegador para exibir dados do Activity Map no contexto do site. Este recurso não está disponível para implementações do SDK da web.

## Habilitar a configuração do conjunto de relatórios

Um conjunto de relatórios deve ter os relatórios do Activity Map habilitados antes do início da coleta de dados. Se a implementação enviar dados do Activity Map para um conjunto de relatórios sem os relatórios do Activity Map habilitados, os dados do Activity Map não serão incluídos na ocorrência.

**[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]** > Selecionar conjunto de relatórios > **[!UICONTROL Editar configurações]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Relatórios do Activity Map]** > **[!UICONTROL Habilitar relatórios do Activity Map]**

Habilitar relatórios do Activity Map cria diversas variáveis reservadas de backend. Consulte [Relatórios do Activity Map](/help/admin/tools/manage-rs/edit-settings/activity-map.md) no guia de administração do Adobe Analytics para obter mais informações.

## Instalação do código

A implementação deve estar configurada corretamente para enviar dados do Activity Map para a Adobe. A extensão de sobreposição do navegador não está disponível quando o Adobe Analytics é implementado com o SDK da web.

+++Extensão da tag do SDK da web

A coleta de dados do Activity Map exige a extensão v2.23 ou posterior do **[!UICONTROL SDK da web da Adobe Experience Platform]**. As versões da extensão até a v2.16 têm suporte limitado. Essas versões anteriores da extensão enviam dados do Activity Map em um evento separado do restante dos dados. Esse evento extra aumenta o número de ocorrências enviadas para o Adobe Analytics ou para a Adobe Experience Platform.

A definição **[!UICONTROL Coleta de dados de cliques]** lida com a coleta de dados do Activity Map e é normalmente habilitada por padrão. É possível verificar e se certificar de que a opção está habilitada nas configurações da extensão:

1. Faça logon no [Adobe CX Enterprise](https://experience.adobe.com) usando suas credenciais da Adobe ID.
1. Selecione **[!UICONTROL Coleta de dados]** no menu de acesso rápido ou no seletor de produtos no canto superior direito.
1. Selecione **[!UICONTROL Tags]** menu de navegação à esquerda.
1. Selecione a tag desejada para editar.
1. Selecione **[!UICONTROL Extensões]** no menu de navegação à esquerda.
1. Selecione **[!UICONTROL SDK da web da Adobe Experience Platform]** na lista de extensões instaladas e escolha **[!UICONTROL Configurar]** à direita.
1. Localize a seção denominada [!UICONTROL Coleta de Dados] e verifique se a caixa de seleção **[!UICONTROL Habilitar coleta de dados de cliques]** está habilitada.
1. Selecione **[!UICONTROL Salvar]**.
1. Se necessário, compile as alterações em uma biblioteca e publique-as na produção.

Consulte [Configurar a extensão de tags do SDK da web](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) para obter mais informações.

+++

+++Biblioteca JavaScript do SDK da web (`alloy.js`)

A coleta de dados do Activity Map exige a biblioteca JavaScript do SDK da web v.2.20 ou posterior. As versões da biblioteca até a v2.15 têm suporte limitado. Essas versões anteriores da biblioteca enviam dados do Activity Map em um evento separado do restante dos dados. Esse evento extra aumenta o número de ocorrências enviadas para o Adobe Analytics ou para a Adobe Experience Platform.

A variável de configuração [`clickCollectionEnabled`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) do SDK da web trata a coleta automática de dados do Activity Map. Ela é habilitada por padrão, a menos que explicitamente desabilitada.

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Extensão de tag do Adobe Analytics

A configuração **[!UICONTROL Usar Activity Map]** lida com a coleta de dados do Activity Map e é normalmente habilitada por padrão. Está disponível para todas as extensões de tags v1.9.0 ou posterior. É possível verificar e se certificar de que a opção está habilitada nas configurações da extensão:

1. Faça logon no [Adobe CX Enterprise](https://experience.adobe.com) usando suas credenciais da Adobe ID.
1. Selecione **[!UICONTROL Coleta de dados]** no menu de acesso rápido ou no seletor de produtos no canto superior direito.
1. Selecione **[!UICONTROL Tags]** menu de navegação à esquerda.
1. Selecione a tag desejada para editar.
1. Selecione **[!UICONTROL Extensões]** no menu de navegação à esquerda.
1. Selecione **[!UICONTROL Adobe Analytics]** na lista de extensões instaladas e escolha **[!UICONTROL Configurar]** à direita.
1. Verifique se a caixa de seleção **[!UICONTROL Usar Activity Map]** está habilitada.
1. Selecione **[!UICONTROL Salvar]**.
1. Se necessário, compile as alterações em uma biblioteca e publique-as na produção.

Consulte a [visão geral da extensão do Adobe Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/analytics/overview) para mais informações.

+++

+++Biblioteca JavaScript do Adobe Analytics (`AppMeasurement.js`)

O módulo Activity Map lida com a coleta de dados do Activity Map e está incluído em todas as bibliotecas AppMeasurement v1.6 ou posterior. É possível inspecionar o arquivo `AppMeasurement.js` para certificar-se de que ele está incluído.

1. Navegue até a [versão mais recente do Adobe Analytics AppMeasurement](https://github.com/adobe/appmeasurement/releases/latest) no GitHub.
1. Faça download do arquivo da biblioteca AppMeasurement compactado e abra `AppMeasurement.js`, que está contido nele.
1. O módulo Activity Map está incluído próximo à parte superior desse arquivo. Certifique-se de que esse módulo esteja incluído na biblioteca do AppMeasurement que seu site usa.

+++

## Dimensões disponíveis

Quando o Activity Map for habilitado para o conjunto de relatórios e a implementação, será possível usar as seguintes dimensões no Analysis Workspace:

* [[!UICONTROL Link do Activity Map]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Região do Activity Map]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Página do Activity Map]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Link do Activity Map por região]](/help/components/dimensions/activity-map-link-by-region.md)

## Baixar e instalar a extensão ou o complemento do navegador

Além das dimensões disponíveis no Analysis Workspace, também é possível visualizar os dados do Activity Map como uma sobreposição no site. Para visualizar essa sobreposição, baixe e instale a extensão ou o complemento do navegador do Activity Map.

**[!UICONTROL Ferramentas]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Baixar Activity Map]**

Esse link direciona para o marketplace da extensão ou do complemento compatível com o navegador, onde é possível fazer a instalação. Após a instalação, a extensão ou o complemento será exibido na parte superior direita do navegador, onde é possível fazer logon e habilitar a sobreposição.
