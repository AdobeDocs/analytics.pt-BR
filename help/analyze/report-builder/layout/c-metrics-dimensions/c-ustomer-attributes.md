---
description: Os atributos do cliente são armazenados em um novo tipo de elemento chamado VisAttr, que pode ser configurado como uma dimensão ou uma métrica.
title: Atributos do cliente
uuid: a8340b83-d7ba-46fe-bb20-b546cdf375b8
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 100%

---

# Atributos do cliente

Os atributos do cliente são armazenados em um novo tipo de elemento chamado VisAttr, que pode ser configurado como uma dimensão ou uma métrica.

Para obter informações detalhadas sobre como fazer upload dos atributos do cliente, consulte a ajuda da [Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=pt-BR).

* Se for configurada como métrica, a VisAttr é exposta como &quot;dimensão&quot; e métrica.

   ![](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Comporta o mesmo detalhamento que uma eVar (qualquer item pode ser detalhado por qualquer coisa).
* A VisAttr é compatível com todas as métricas de eVar.
* A VisAttr como uma métrica suporta a &quot;compartimentalização&quot; (como Tempo no site: 0 a 30, 31 a 60…)
* A VisAttr está disponível como uma dimensão de segmentação.
