---
title: Implementar o Adobe Analytics usando o SDK móvel da Adobe Experience Platform
description: Use a extensão SDK móvel na coleção de dados da Adobe Experience Platform para enviar dados ao Adobe Analytics.
source-git-commit: 5adc3fe1eab0a358573ebdc12e51c6753e85b14c
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 20%

---

# Implementar o Adobe Analytics usando o SDK móvel da Adobe Experience Platform

O SDK móvel da Adobe Experience Platform ajuda a potencializar as soluções e os serviços da Experience Cloud em seus aplicativos móveis. Ele está disponível para Android™, iOS e várias estruturas de desenvolvimento entre plataformas. A configuração é feita por meio da Coleção de dados da Adobe Experience Platform.
>[!IMPORTANT]
>
>Uma extensão do Adobe Analytics também está disponível na Coleção de dados da Adobe Experience Platform. Se você instalar essa extensão, não será possível usar o XDM ou a Rede de borda.

## Adobe Experience Platform SDK

Uma visão geral de alto nível das tarefas de implementação:

![Adobe Analytics usando o fluxo de trabalho de extensão do Analytics](../../assets/mobilesdk-annotated.png)

| | Tarefa | Mais Informações | |-| —| | 1 | Certifique-se de que **definiu um conjunto de relatórios**. | [Gerenciador do Conjunto de relatórios](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configurar esquemas e conjuntos de dados**. Para padronizar a coleta de dados para uso em aplicativos que utilizam o Adobe Experience Platform, o Adobe criou o padrão aberto e documentado publicamente, o Experience Data Model (XDM). | [Configurar esquemas e conjuntos de dados](https://developer.adobe.com/client-sdks/documentation/getting-started/set-up-schemas-and-datasets/) | | 3 | **Configurar um conjunto de dados**. Um armazenamento de dados representa a configuração do lado do servidor ao implementar o SDK da Web da Adobe Experience Platform. | [Configurar um conjunto de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 4 | **Adicionar um serviço Adobe Analytics** ao armazenamento de dados. Esse serviço controla se e como os dados são enviados para a Adobe Analytics. | [Adicionar o serviço Adobe Analytics a um armazenamento de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 5 | **Criar uma propriedade móvel**. Uma propriedade é um container que você preenche com extensões, regras, elementos de dados e bibliotecas. | [Configurar uma propriedade móvel](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 6 | **Instale a extensão Rede de borda do Adobe Experience Platform** na propriedade da tag para dispositivos móveis e configure o conjunto de dados na extensão . | [Rede de borda Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/edge-network/) | | 7 | **Usar código no aplicativo** para registrar as extensões necessárias e carregar a configuração da tag. | [Configurar a configuração](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 8 | **Implementar e testar a funcionalidade** usando a combinação de elementos de dados da tag , regras, extensões adicionais e chamadas da API do SDK no seu aplicativo. Inspect, valide e depure a coleta de dados e as experiências do aplicativo móvel. | [Usar o aplicativo de amostra](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 9 | **Estender e validar a implementação do aplicativo móvel** antes de empurrá-lo para a produção. | |


## Extensão do Adobe Analytics.

Uma visão geral de alto nível das tarefas de implementação:

![Adobe Analytics usando o fluxo de trabalho de extensão do Analytics](../../assets/mobilesdk-analytics-annotated.png)

| | Tarefa | Mais Informações | |-| —| | 1 | Certifique-se de que **definiu um conjunto de relatórios**. | [Gerenciador do Conjunto de relatórios](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Criar uma propriedade móvel**. Uma propriedade é um container que você preenche com extensões, regras, elementos de dados e bibliotecas. | [Configurar uma propriedade móvel](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 3 | **Instalar a extensão Adobe Analytics** na propriedade da tag para dispositivos móveis e configure a extensão para apontar para o conjunto de relatórios. | [Extensão do Adobe Analytics para propriedade móvel](https://developer.adobe.com/client-sdks/documentation/adobe-analytics/) | | 4 | **Usar código no aplicativo** para registrar as extensões necessárias e carregar a configuração da tag. | [Configurar a configuração](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 5 | **Implementar e testar a funcionalidade** usando a combinação de elementos de dados da tag , regras, extensões adicionais e chamadas da API do SDK no seu aplicativo. Inspect, valide e depure a coleta de dados e as experiências do aplicativo móvel. | [Usar o aplicativo de amostra](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 6 | **Estender e validar a implementação do aplicativo móvel** antes de empurrá-lo para a produção. | |

## Recursos adicionais

- [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR#)

- [Documentação do SDK móvel](https://developer.adobe.com/client-sdks/documentation/)



