---
description: Os dados de segmentação geográfica são registrados com base na primeira ocorrência da visita e não são alterados para uma visita única, independentemente do dispositivo usado.
keywords: Implementação do Analytics
seo-description: Os dados de segmentação geográfica são registrados com base na primeira ocorrência da visita e não são alterados para uma visita única, independentemente do dispositivo usado.
seo-title: Dados de segmentação geográfica
solution: Analytics
title: Dados de segmentação geográfica
topic: Desenvolvedor e implementação
uuid: 8449bf11-c367-4698-a73e-f6cb59f8c945
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Dados de segmentação geográfica

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte a [Documentação de cooperação do dispositivo da Adobe Experience Cloud](https://marketing.adobe.com/resources/help/pt_BR/mcdc/).

Os dados de segmentação geográfica são registrados com base na primeira ocorrência da visita e não são alterados para uma visita única, independentemente do dispositivo usado.

Se um cliente procura seu site por um computador pessoal e 30 minutos depois de um dispositivo móvel, os dados de segmentação geográfica não são alterados. Se você estiver usando o VISTA para preencher uma eVar com dados de geossegmentação, ele se baseará no endereço IP de cada hit. Isso pode resultar em vários valores de dados de geossegmentação, caso o endereço IP seja alterado para a mesma visita.
