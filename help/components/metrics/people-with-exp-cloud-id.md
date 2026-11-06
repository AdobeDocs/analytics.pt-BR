---
title: Pessoas com Experience Cloud ID
description: O número de pessoas na Análise entre dispositivos que têm uma ECID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
TQID: https://experienceleague.adobe.com/w85poHKHnDYQ0iTItr2r26q1aRpN50AsdYzg6v82Jpk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 0ba418a49e6a226540e0791f0138027566022d6f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 28%
---
# Pessoas com Experience Cloud ID

&quot;Pessoas com Experience Cloud ID&quot; é uma métrica da [Análise entre dispositivos](../cda/overview.md) que mostra o número de [Pessoas](people.md) identificadas pela Adobe usando o [Serviço de ID de Visitante](https://experienceleague.adobe.com/pt-br/docs/id-service/using/home) ou o [Web SDK](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/identity/overview).

## Como essa métrica é calculada

Considerando cada [Pessoas](people.md) (identificadas ou não identificadas), esta [métrica](overview.md) aumenta se a ocorrência contiver a cadeia de caracteres de consulta `mid` (com base no cookie [`s_ecid`](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/cookies/analytics)).

Você pode criar a métrica calculada `[People with ECID] ÷ [People]` para obter a porcentagem de visitantes do site usando o serviço de ID.

Consulte a métrica equivalente não CDA [Visitantes com Experience Cloud ID](visitors-with-ecid.md) para obter mais informações sobre a importância da ECID e depurar sua configuração.
