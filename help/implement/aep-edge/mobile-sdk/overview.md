---
title: Implementar o Adobe Analytics usando o SDK móvel da Adobe Experience Platform
description: Use a extensão SDK móvel na coleção de dados da Adobe Experience Platform para enviar dados ao Adobe Analytics.
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: ht
source-wordcount: '206'
ht-degree: 100%

---

# Implementar o Adobe Analytics usando o SDK móvel da Adobe Experience Platform

O SDK móvel da Adobe Experience Platform ajuda a potencializar as soluções e os serviços da Experience Cloud em seus aplicativos móveis. Ele está disponível para Android, iOS e várias estruturas de desenvolvimento entre plataformas. A configuração é feita por meio da Coleção de dados da Adobe Experience Platform.

Para enviar dados para a Adobe Experience Edge usando o SDK móvel:

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection).
2. Selecione a propriedade desejada na lista ou [configure uma propriedade móvel](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).
3. Acesse a guia Extensões e instale a extensão [Identidade da rede de borda](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network).
4. Instale a [Rede de borda da Adobe Experience Platform](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension).
5. [Configure um conjunto de dados](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams) adicionando o Adobe Analytics como um serviço apontando para o conjunto de relatórios desejado.
6. [Instale o SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) no aplicativo móvel.

>[!IMPORTANT]
>
>Uma extensão do Adobe Analytics também está disponível na Coleção de dados da Adobe Experience Platform. Se você instalar essa extensão, não será possível usar o XDM ou a Rede de borda.
