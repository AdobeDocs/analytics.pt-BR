---
description: O Analytics conta uma visita sempre que uma chamada de servidor ocorre com um Número de página de visita igual a 1.
keywords: Implementação do Analytics
seo-description: O Analytics conta uma visita sempre que uma chamada de servidor ocorre com um Número de página de visita igual a 1.
seo-title: Visitas
solution: Analytics
subtopic: Visitantes
title: Visitas
topic: Desenvolvedor e implementação
uuid: 3035 be 8 f -6 adc -45 df-a 3 f 2-5 de 6 d 3 ed 99 ce
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Visitas

>[!IMPORTANT]
>
>Não é mais recomendado este método de identificação de visitantes em dispositivos. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

O Analytics conta uma visita sempre que uma chamada de servidor ocorre com um Número de página de visita igual a 1.

If you look at the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), this occurred 4 times: at hits 1, 9, 11, and 12. Similar aos visitantes, este valor volta ao normal depois da associação inicial, pois o [!UICONTROL Número de página da visita] é redefinido a 1 devido a uma alteração na [!UICONTROL ID de visitante] efetiva.
