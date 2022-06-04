---
title: Implementar o Adobe Analytics usando o Adobe Experience Platform Web SDK
description: Use a extensão SDK da Web na Coleta de dados do Adobe Experience Platform para enviar dados ao Adobe Analytics.
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 33%

---


# Implementar o Adobe Analytics usando o Adobe Experience Platform Web SDK

Você pode usar o [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=pt-BR) para enviar dados ao Adobe Analytics. Esse método de implementação funciona traduzindo o [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR) em um formato usado pelo Analytics.

## Configuração

Para configurar o Analytics para receber dados XDM:

1. Instale e [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) o [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=pt-BR).

1. Certifique-se de que os conjuntos de relatórios aplicáveis sejam mapeados para os dados desejados. Os dados XDM fluem automaticamente para o conjunto de relatórios do Adobe Experience Edge.
