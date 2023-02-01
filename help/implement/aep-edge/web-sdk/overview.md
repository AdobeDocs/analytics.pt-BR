---
title: Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform
description: Use a extensão SDK da Web na coleção de dados da Adobe Experience Platform para enviar dados ao Adobe Analytics.
source-git-commit: 472faef9c6ef99d4e58f2f5a9a71ca8d058f0ee2
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 23%

---

# Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform

Você pode usar o [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) para enviar dados ao Adobe Analytics. Este método de implementação funciona traduzindo o [Modelo de dados de experiência (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR) em um formato usado pelo Analytics.

Você pode enviar dados para o Experience Edge diretamente usando o SDK da Web ou por meio da extensão SDK da Web em Tags.

## SDK da Web

Uma visão geral de alto nível das tarefas de implementação:

![Implementar o Adobe Analytics usando o fluxo de trabalho do SDK da Web](../../assets/websdk-annotated.png)

| | Tarefa | Mais Informações | |-| —| | 1 | Certifique-se de que **definiu um conjunto de relatórios**. | [Gerenciador do Conjunto de relatórios](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configurar esquemas e conjuntos de dados**. Para padronizar a coleta de dados para uso em aplicativos que utilizam o Adobe Experience Platform, o Adobe criou o padrão aberto e documentado publicamente, o Experience Data Model (XDM). | [Visão geral da interface do usuário de esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=pt-BR) e [Visão geral da interface do usuário de conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=pt-BR) | | 3 | **Criar uma camada de dados** para gerenciar o rastreamento dos dados no seu site. | [Criar uma camada de dados](../../prepare/data-layer.md) | | 4 | **Instalar a versão independente pré-criada**. Você pode fazer referência à biblioteca (`alloy.js`) na CDN diretamente na sua página ou baixe e hospede-a em sua própria infraestrutura. Como alternativa, você pode usar o pacote NPM. | [Instalação da versão independente pré-criada](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version) e [Uso do pacote NPM](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package)| | 5 | **Configurar um conjunto de dados**. Um armazenamento de dados representa a configuração do lado do servidor ao implementar o SDK da Web da Adobe Experience Platform. | [Configurar um conjunto de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 6 | **Adicionar um serviço Adobe Analytics** ao armazenamento de dados. Esse serviço controla se e como os dados são enviados para a Adobe Analytics. | [Adicionar o serviço Adobe Analytics a um armazenamento de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 7 | **Configurar o SDK da Web**. Certifique-se de que a biblioteca instalada na etapa 4 esteja configurada corretamente com a ID do armazenamento de dados (anteriormente conhecida como ID de configuração de borda (`edgeConfigId`), id da organização (`orgId`) e outras opções disponíveis. | [Configurar o SDK da Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) | | 8 | **Executar comandos** e/ou **rastrear eventos**. Depois que o código base tiver sido implementado em sua página da Web, você poderá começar a executar comandos e rastrear eventos com o SDK. | [Executar comandos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en) e [Rastrear eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en) | | 9 | **Estender e validar sua implementação** antes de empurrá-lo para a produção. | |



## Extensão do SDK da Web

Uma visão geral de alto nível das tarefas de implementação:

![Implementar o Adobe Analytics usando o fluxo de trabalho da extensão do SDK da Web](../../assets/websdk-extension-annotated.png)

| | Tarefa | Mais Informações | |-| —| | 1 | Certifique-se de que **definiu um conjunto de relatórios**. | [Gerenciador do Conjunto de relatórios](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configurar esquemas e conjuntos de dados**. Para padronizar a coleta de dados para uso em aplicativos que utilizam o Adobe Experience Platform, o Adobe criou o padrão aberto e documentado publicamente, o Experience Data Model (XDM). | [Visão geral da interface do usuário de esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=pt-BR) e [Visão geral da interface do usuário de conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=pt-BR) | | 3 | **Criar uma camada de dados** para gerenciar o rastreamento dos dados no seu site. | [Criar uma camada de dados](../../prepare/data-layer.md) | | 4 | **Configurar um conjunto de dados**. Um armazenamento de dados representa a configuração do lado do servidor ao implementar o SDK da Web da Adobe Experience Platform. | [Configurar um conjunto de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 5 | **Adicionar um serviço Adobe Analytics** ao armazenamento de dados. Esse serviço controla se e como os dados são enviados para a Adobe Analytics. | [Adicionar o serviço Adobe Analytics a um armazenamento de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 6 | **Criar uma propriedade de tag**. As propriedades são contêineres abrangentes usados para fazer referência aos dados do gerenciamento de tags.| [Criar ou configurar uma propriedade de tag para a Web](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web) | | 7 | **Instalar e configurar a extensão Web SDK** na propriedade da tag. Configure a extensão SDK da Web para enviar dados para o conjunto de dados configurado na etapa 4. | [Visão geral da extensão do Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en) | | 8 | **Iterar, validar e publicar** à produção. Adicione a propriedade da tag ao seu site. Em seguida, use elementos de dados, regras e assim por diante, para personalizar sua implementação. | [Visão geral da publicação](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=pt-BR) |



## Recursos adicionais

As tags podem ser altamente personalizadas. Saiba mais sobre como aproveitar ao máximo o Adobe Analytics, incluindo os dados corretos na implementação.

- [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR#): saiba como a interface funciona e quais extensões estão disponíveis.

- [Documentação do SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=pt-BR)
