---
title: Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform
description: Use o Web SDK para enviar dados ao Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/4pS-q3F3W7D1ojdMkCzgUyZkO3LDt1DpFfxqcTtZXLQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 42%

---

# Implementar o Adobe Analytics usando o SDK da Web da Adobe Experience Platform

Você pode usar o [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) para enviar dados ao Adobe Analytics. Há dois métodos principais para implementar o Web SDK, e cada método tem dois tipos de implementação:

| | **Migrar do AppMeasurement** | **Implementação do Clean Web SDK** |
| --- | --- | --- |
| **Usar marcas** | [Migrar da extensão do Analytics para a extensão do Web SDK](analytics-extension-to-web-sdk.md) | [Enviar dados para o Adobe Analytics usando a extensão do Web SDK](web-sdk-tag-extension.md) |
| **Usar JavaScript** | [Migrar do AppMeasurement para a biblioteca JavaScript da Web SDK](appmeasurement-to-web-sdk.md) | [Enviar dados para a Adobe Analytics usando a biblioteca JavaScript da Web SDK](web-sdk-javascript-library.md) |

Se sua organização exigir uma nova implementação do Web SDK e planejar usar o Customer Journey Analytics no futuro, a Adobe recomenda uma implementação limpa do Web SDK usando seu próprio esquema. Consulte [Assimilar dados por meio do Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) no guia do usuário do Customer Journey Analytics.

## Recursos adicionais

As tags podem ser altamente personalizadas. Saiba mais sobre como aproveitar ao máximo o Adobe Analytics, incluindo os dados corretos na implementação.

- [Documentação de tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR#): saiba como a interface funciona e quais extensões estão disponíveis.

- [Documentação do Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=pt-BR)
