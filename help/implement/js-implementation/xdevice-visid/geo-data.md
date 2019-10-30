---
description: Os dados de segmentação geográfica são registrados com base na primeira ocorrência da visita e não são alterados para uma visita única, independentemente do dispositivo usado.
keywords: Implementação do Analytics
seo-description: Os dados de segmentação geográfica são registrados com base na primeira ocorrência da visita e não são alterados para uma visita única, independentemente do dispositivo usado.
seo-title: Dados de segmentação geográfica
solution: Analytics
title: Dados de segmentação geográfica
topic: Desenvolvedor e implementação
uuid: 8449bf11-c367-4698-a73e-f6cb59f8c945
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Dados de segmentação geográfica

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte a Documentação [do Device Co-op da](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud.

Os dados de segmentação geográfica são registrados com base na primeira ocorrência da visita e não são alterados para uma visita única, independentemente do dispositivo usado.

Se um cliente procura seu site por um computador pessoal e 30 minutos depois de um dispositivo móvel, os dados de segmentação geográfica não são alterados. Se você estiver usando o VISTA para preencher uma eVar com dados de geossegmentação, ele se baseará no endereço IP de cada hit. Isso pode resultar em vários valores de dados de geossegmentação, caso o endereço IP seja alterado para a mesma visita.
