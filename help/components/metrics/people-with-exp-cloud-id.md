---
title: Pessoas com Experience Cloud ID
description: O número de pessoas na Análise entre dispositivos que têm um Experience Cloud ID.
source-git-commit: eaf0c3b751a5fbdc70ad6bef501dbf9e8400339c
workflow-type: ht
source-wordcount: '130'
ht-degree: 100%

---

# Pessoas com Experience Cloud ID

&quot;Pessoas com Experience Cloud ID&quot; é uma métrica de [Análise entre dispositivos](../cda/overview.md) que mostra o número de [Pessoas](people.md) que foram identificadas pela Adobe usando o [serviço Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR).

## Como essa métrica é calculada

Considerando cada [Pessoas](people.md) (identificadas ou não identificadas), essa métrica aumenta se o hit contiver a sequência de consulta `mid` (com base no cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=pt-BR)).

Você pode criar a métrica calculada `[People with ECID] ÷ [People]` para obter a porcentagem de visitantes do site usando o serviço de ID.

Consulte a métrica equivalente não CDA [Visitantes com Experience Cloud ID](visitors-with-ecid.md) para obter mais informações sobre a importância da Experience Cloud ID e depurar sua configuração.
