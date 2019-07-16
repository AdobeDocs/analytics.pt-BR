---
description: Os dados de segmentação geográfica são registrados com base na primeira ocorrência da visita e não são alterados para uma visita única, independentemente do dispositivo usado.
keywords: Implementação do Analytics
seo-description: Os dados de segmentação geográfica são registrados com base na primeira ocorrência da visita e não são alterados para uma visita única, independentemente do dispositivo usado.
seo-title: Dados de segmentação geográfica
solution: Analytics
title: Dados de segmentação geográfica
topic: Desenvolvedor e implementação
uuid: 8449 bf 11-c 367-4698-a 73 e-f 6 cb 59 f 8 c 945
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Dados de segmentação geográfica

>[!IMPORTANT]
>
>Não é mais recomendado este método de identificação de visitantes em dispositivos. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Os dados de segmentação geográfica são registrados com base na primeira ocorrência da visita e não são alterados para uma visita única, independentemente do dispositivo usado.

Se um cliente procura seu site por um computador pessoal e 30 minutos depois de um dispositivo móvel, os dados de segmentação geográfica não são alterados. Se você estiver usando o VISTA para preencher uma evar com dados de segmentação geográfica, ele se baseará no endereço IP em cada ocorrência. Isso pode resultar em vários valores de dados de segmentação geográfica se o endereço IP mudar para a mesma visita.
