---
description: Você pode criar um segmento sempre que uma associação ocorrer para um determinado cookie de ID do visitante.
keywords: Analytics Implementation
solution: Analytics
title: Criar segmentos
topic: Developer and implementation
uuid: 476a4667-033c-4e53-961d-ad67e7c2b045
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Criar segmentos

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte a Documentação [do Device Co-op da](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

Você pode criar um segmento sempre que uma associação ocorrer para um determinado cookie de ID do visitante.

Com base na [tabela anterior](/help/implement/js-implementation/xdevice-visid/visit-example.md), se você criou um segmento em que o número de visitas é igual a 9, ele incluiria as chamadas do servidor 12 e 13. Mesmo que a chamada 11 do servidor seja parte tecnicamente da mesma visita, os dados históricos dessa chamada do servidor não serão alterados e o número da visita permanecerá sem alteração.
