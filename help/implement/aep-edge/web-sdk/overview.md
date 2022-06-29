---
title: Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform
description: Use a extensão SDK da Web na coleção de dados da Adobe Experience Platform para enviar dados ao Adobe Analytics.
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---


# Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform

Você pode usar o [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=pt-BR) para enviar dados ao Adobe Analytics. Este método de implementação funciona traduzindo o [Modelo de dados de experiência (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR) em um formato usado pelo Analytics.

## Configuração

Para configurar o Analytics para receber dados XDM:

1. Instale e [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) o [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=pt-BR).

1. Verifique se os conjuntos de relatórios aplicáveis estão mapeados para os dados desejados. Os dados XDM fluem automaticamente para o conjunto de relatórios da Adobe Experience Platform.Edge.
