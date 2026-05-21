---
title: Pessoas com Experience Cloud ID
description: O número de pessoas na Análise entre dispositivos que têm um Experience Cloud ID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
TQID: https://experienceleague.adobe.com/w85poHKHnDYQ0iTItr2r26q1aRpN50AsdYzg6v82Jpk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 85%

---

# Pessoas com Experience Cloud ID

&quot;Pessoas com Experience Cloud ID&quot; é uma métrica de [Análise entre dispositivos](../cda/overview.md) que mostra o número de [Pessoas](people.md) que foram identificadas pela Adobe usando o [serviço Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR).

## Como essa métrica é calculada

Considerando cada [Pessoas](people.md) (identificadas ou não identificadas), esta [métrica](overview.md) aumenta se a ocorrência contiver a cadeia de caracteres de consulta `mid` (com base no cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=pt-BR)).

Você pode criar a métrica calculada `[People with ECID] ÷ [People]` para obter a porcentagem de visitantes do site usando o serviço de ID.

Consulte a métrica equivalente não CDA [Visitantes com Experience Cloud ID](visitors-with-ecid.md) para obter mais informações sobre a importância da Experience Cloud ID e depurar sua configuração.
