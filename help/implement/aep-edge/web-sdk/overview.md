---
title: Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform
description: Use o SDK da Web para enviar dados para a Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: d6c16d8841110e3382248f4c9ce3c2f2e32fe454
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 40%

---

# Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform

Você pode usar o [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) para enviar dados ao Adobe Analytics. Há dois métodos principais para implementar o SDK da Web e cada método tem dois tipos de implementação:

| | **Migrar do AppMeasurement** | **Implementação do SDK da Web limpo** |
| --- | --- | --- |
| **Usar marcas** | [Migrar da extensão do Analytics para a extensão do SDK da Web](analytics-extension-to-web-sdk.md) | [Enviar dados para a Adobe Analytics usando a extensão SDK da Web](web-sdk-tag-extension.md) |
| **Usar JavaScript** | [Migrar do AppMeasurement para a biblioteca JavaScript do SDK da Web](appmeasurement-to-web-sdk.md) | [Enviar dados para a Adobe Analytics usando a biblioteca JavaScript do SDK da Web](web-sdk-javascript-library.md) |

Se sua organização exigir uma nova implementação do SDK da Web e planeja usar o Customer Journey Analytics no futuro, o Adobe recomenda uma implementação limpa do SDK da Web usando seu próprio esquema. Consulte [Assimilar dados por meio do SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) no guia do usuário Customer Journey Analytics.

## Recursos adicionais

As tags podem ser altamente personalizadas. Saiba mais sobre como aproveitar ao máximo o Adobe Analytics, incluindo os dados corretos na implementação.

- [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR#): saiba como a interface funciona e quais extensões estão disponíveis.

- [Documentação do SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=pt-BR)
