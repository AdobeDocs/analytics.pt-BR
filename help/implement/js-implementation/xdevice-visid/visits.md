---
description: O Analytics conta uma visita sempre que uma chamada de servidor ocorre com um Número de página de visita igual a 1.
keywords: Implementação do Analytics
seo-description: O Analytics conta uma visita sempre que uma chamada de servidor ocorre com um Número de página de visita igual a 1.
seo-title: Visitas
solution: Analytics
subtopic: Visitantes
title: Visitas
topic: Desenvolvedor e implementação
uuid: 3035be8f-6adc-45df-a3f2-5de6d3ed99ce
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Visitas

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte a Documentação [do Device Co-op da](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

O Analytics conta uma visita sempre que uma chamada de servidor ocorre com um Número de página de visita igual a 1.

Se você observar a [tabela anterior](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), isso ocorreu 4 vezes: nos hits 1, 9, 11 e 12. Similar aos visitantes, este valor volta ao normal depois da associação inicial, pois o [!UICONTROL Número de página da visita] é redefinido a 1 devido a uma alteração na [!UICONTROL ID de visitante] efetiva.
