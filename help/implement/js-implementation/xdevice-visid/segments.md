---
description: Você pode criar um segmento sempre que uma associação ocorrer para um determinado cookie de ID do visitante.
keywords: Implementação do Analytics
seo-description: Você pode criar um segmento sempre que uma associação ocorrer para um determinado cookie de ID do visitante.
seo-title: Criar segmentos
solution: Analytics
title: Criar segmentos
topic: Desenvolvedor e implementação
uuid: 476 a 4667-033 c -4 e 53-961 d-ad 67 e 7 c 2 b 045
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Criar segmentos

>[!IMPORTANT]
>
>Não é mais recomendado este método de identificação de visitantes em dispositivos. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Você pode criar um segmento sempre que uma associação ocorrer para um determinado cookie de ID do visitante.

Based on the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), if you created a segment where visit number equals 9, it would include server calls 12 and 13. Mesmo que a chamada 11 do servidor seja parte tecnicamente da mesma visita, os dados históricos dessa chamada do servidor não serão alterados e o número da visita permanecerá sem alteração.
