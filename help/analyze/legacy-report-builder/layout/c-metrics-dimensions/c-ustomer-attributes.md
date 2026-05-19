---
description: Os atributos do cliente são armazenados em um novo tipo de elemento chamado VisAttr, que pode ser configurado como uma dimensão ou uma métrica.
title: Atributos do cliente
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
TQID: https://experienceleague.adobe.com/J-KoYBPg-bECW1utOk2L0YLtBWd9-jHT6gwAEm54fs4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 135
ht-degree: 69%

---

# Atributos do cliente

{{legacy-arb}}

Os atributos do cliente são armazenados em um novo tipo de elemento chamado VisAttr, que pode ser configurado como uma dimensão ou uma métrica.

Para obter informações detalhadas sobre como fazer upload dos atributos do cliente, consulte a [ajuda do CX Enterprise](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=pt-BR).

* Se for configurada como métrica, a VisAttr é exposta como métrica e &quot;dimensão&quot;.

  ![Captura de tela mostrando a métrica e os atributos do cliente da dimensão.](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Comporta o mesmo detalhamento que uma eVar (qualquer item pode ser detalhado por qualquer coisa).
* A VisAttr é compatível com todas as métricas do eVar.
* A VisAttr como uma métrica suporta a &quot;compartimentalização&quot; (como Tempo no site: 0 a 30, 31 a 60…)
* A VisAttr está disponível como uma dimensão de segmentação.
