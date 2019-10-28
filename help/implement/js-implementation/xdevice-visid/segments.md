---
description: Você pode criar um segmento sempre que uma associação ocorrer para um determinado cookie de ID do visitante.
keywords: Implementação do Analytics
seo-description: Você pode criar um segmento sempre que uma associação ocorrer para um determinado cookie de ID do visitante.
seo-title: Criar segmentos
solution: Analytics
title: Criar segmentos
topic: Desenvolvedor e implementação
uuid: 476a4667-033c-4e53-961d-ad67e7c2b045
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Criar segmentos

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte a [Documentação de cooperação do dispositivo da Adobe Experience Cloud](https://marketing.adobe.com/resources/help/pt_BR/mcdc/).

Você pode criar um segmento sempre que uma associação ocorrer para um determinado cookie de ID do visitante.

Com base na [tabela anterior](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), se você criou um segmento em que o número de visitas é igual a 9, ele incluiria as chamadas do servidor 12 e 13. Mesmo que a chamada 11 do servidor seja parte tecnicamente da mesma visita, os dados históricos dessa chamada do servidor não serão alterados e o número da visita permanecerá sem alteração.
