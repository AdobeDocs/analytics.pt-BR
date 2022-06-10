---
title: Implementar o Adobe Analytics usando o Adobe Experience Platform Mobile SDK
description: Use a extensão Mobile SDK na Coleta de dados do Adobe Experience Platform para enviar dados ao Adobe Analytics.
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 3%

---

# Implementar o Adobe Analytics usando o Adobe Experience Platform Mobile SDK

O SDK do Adobe Experience Platform Mobile ajuda a potencializar as soluções e os serviços do Experience Cloud em seus aplicativos móveis. Ele está disponível para Android, iOS e várias estruturas de desenvolvimento entre plataformas. A configuração é realizada por meio da Coleta de dados da Adobe Experience Platform.

Para enviar dados para o Adobe Experience Edge usando o Mobile SDK:

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection).
2. Selecione a propriedade desejada na lista ou [configurar uma propriedade móvel](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).
3. Acesse a guia Extensões e instale o [Identidade da rede Edge](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network) extensão.
4. Instale o [Rede de borda Adobe Experience Platform](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension).
5. [Configurar um conjunto de dados](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams), adicionar o Adobe Analytics como um serviço apontando para o conjunto de relatórios desejado.
6. [Instalar o SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) no aplicativo móvel.

>[!IMPORTANT]
>
>Uma extensão Adobe Analytics também está disponível na Coleta de dados da Adobe Experience Platform. Se você instalar essa extensão, não aproveite o XDM ou a Edge Network.
