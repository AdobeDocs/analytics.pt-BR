---
title: Pessoas com Experience Cloud ID
description: O número de pessoas no Cross-Device Analytics que têm uma ID de Experience Cloud.
source-git-commit: eaf0c3b751a5fbdc70ad6bef501dbf9e8400339c
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 21%

---

# Pessoas com Experience Cloud ID

&#39;Pessoas com Experience Cloud ID&#39; é uma métrica de [Análise entre dispositivos](../cda/overview.md) que mostra o número de [Pessoas](people.md) que foram identificadas pelo Adobe usando o [Experience Cloud ID service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR).

## Como essa métrica é calculada

Considerando cada [People](people.md) (identificada ou não identificada), essa métrica aumenta se a ocorrência contiver a sequência de consulta `mid` (com base no cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=pt-BR)).

Você pode criar a métrica calculada `[People with ECID] ÷ [People]` para obter a porcentagem de visitantes do site usando o serviço de ID.

Consulte a métrica equivalente não CDA [Visitantes com Experience Cloud ID](visitors-with-ecid.md) para obter mais informações sobre a importância da Experience Cloud ID e depurar sua configuração.
